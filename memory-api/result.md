

**问题**
**1．首先，编写一个名为 null.c 的简单程序，它创建一个指向整数的指针，将其设置为NULL，然后尝试对其进行释放内存操作。把它编译成一个名为 null 的可执行文件。当你运行这个程序时会发生什么？**

```c
#include <stdio.h>
#include <stdlib.h>
#include <unistd.h>

int
main(int argc, char *argv[])
{
    int *int_null = NULL;
    free(int_null);
    return 0;
}
```

```sh
[root@localhost hw]# gcc -Wall null.c -o null
[root@localhost hw]# ls
null  null.c
[root@localhost hw]# ./null
[root@localhost hw]# 
```

**2．接下来，编译该程序，其中包含符号信息（使用-g 标志）。这样做可以将本多信息放入可执行文件中，使调试器可以但问有关变量名称等的本多有用信息。通过输入 gdb null，在调试器下运行该程序，然后，一旦 gdb 运行，输入 run。gdb 显示什么信息？**

```sh
(gdb) run
Starting program: /root/OSTEP/memony-api/hw/null 
[Inferior 1 (process 27968) exited normally]
Missing separate debuginfos, use: debuginfo-install glibc-2.17-317.el7.x86_64
```

**3．最后，对这个程序使用 valgrind 工具。我们将使用属于 valgrind 的 memcheck 工具来分析发生的情况。输入以下命令来运行程序：valgrind --leak-check=yes null。当你运行它时会发生什么？你能解释工具的输出吗？**

既没有申请,也没有释放内存

```sh
[root@localhost hw]# valgrind --leak-check=yes ./null
==63415== Command: ./null
==63415== 
==63415== 
==63415== HEAP SUMMARY:
==63415==     in use at exit: 0 bytes in 0 blocks
==63415==   total heap usage: 0 allocs, 0 frees, 0 bytes allocated
==63415== 
==63415== All heap blocks were freed -- no leaks are possible
==63415== 
==63415== For lists of detected and suppressed errors, rerun with: -s
==63415== ERROR SUMMARY: 0 errors from 0 contexts (suppressed: 0 from 0)
```

**4．编写一个使用 malloc()来分配内存的简单程序，但在退出之前忘记释放它。这个程序运行时会发生什么？你可以用 gdb 来查找它的任何问题吗？用 valgrind 那（再次使用--leak-check=yes 标志）？**

gdb无异常

```c
#include <stdio.h>
#include <stdlib.h>
#include <unistd.h>

int
main(int argc, char *argv[])
{
    int *x = malloc(sizeof(int));

    return 0;
}
```

```sh
gcc -Wall -g  null_without_free.c -o null_without_free
Reading symbols from /root/OSTEP/memony-api/hw/null_without_free...done.
(gdb) run
Starting program: /root/OSTEP/memony-api/hw/null_without_free 
[Inferior 1 (process 64360) exited normally]
Missing separate debuginfos, use: debuginfo-install glibc-2.17-317.el7.x86_64
```

报错 4 bytes in 1 blocks are definitely lost in loss record 1 of 1

```sh
==64494== Command: ./null_without_free
==64494== 
==64494== 
==64494== HEAP SUMMARY:
==64494==     in use at exit: 4 bytes in 1 blocks
==64494==   total heap usage: 1 allocs, 0 frees, 4 bytes allocated
==64494== 
==64494== 4 bytes in 1 blocks are definitely lost in loss record 1 of 1
==64494==    at 0x4C2B187: malloc (vg_replace_malloc.c:393)
==64494==    by 0x400545: main (null_without_free.c:8)
==64494== 
==64494== LEAK SUMMARY:
==64494==    definitely lost: 4 bytes in 1 blocks
==64494==    indirectly lost: 0 bytes in 0 blocks
==64494==      possibly lost: 0 bytes in 0 blocks
==64494==    still reachable: 0 bytes in 0 blocks
==64494==         suppressed: 0 bytes in 0 blocks
==64494== 
==64494== For lists of detected and suppressed errors, rerun with: -s
==64494== ERROR SUMMARY: 1 errors from 1 contexts (suppressed: 0 from 0)
```

**5．编写一个程序，使用 malloc 创建一个名为 data、大小为 100 的整数数组。然后，将data[100]设置为 0。当你运行这个程序时会发生什么？当你使用 valgrind 运行这个程序时会发生什么？程序是否正确？**

```sh
#include <stdio.h>
#include <stdlib.h>
#include <unistd.h>

int
main(int argc, char *argv[])
{
    int* data = malloc(sizeof(int)*100);
    data[100] = 0;
    return 0;
}
```

gdb正常退出

```sh
(gdb) run
Starting program: /root/OSTEP/memony-api/hw/data 
[Inferior 1 (process 64912) exited normally]
Missing separate debuginfos, use: debuginfo-install glibc-2.17-317.el7.x86_64
```

报错 

Invalid write of size 4,非法写入,数组越界.

 400 bytes in 1 blocks are definitely lost in loss record 1 of 1 

```sh
valgrind --leak-check=yes ./data
==64986== Memcheck, a memory error detector
==64986== Copyright (C) 2002-2022, and GNU GPL'd, by Julian Seward et al.
==64986== Using Valgrind-3.20.0 and LibVEX; rerun with -h for copyright info
==64986== Command: ./data
==64986== 
==64986== Invalid write of size 4
==64986==    at 0x400554: main (data.c:9)
==64986==  Address 0x520a1d0 is 0 bytes after a block of size 400 alloc'd
==64986==    at 0x4C2B187: malloc (vg_replace_malloc.c:393)
==64986==    by 0x400545: main (data.c:8)
==64986== 
==64986== 
==64986== HEAP SUMMARY:
==64986==     in use at exit: 400 bytes in 1 blocks
==64986==   total heap usage: 1 allocs, 0 frees, 400 bytes allocated
==64986== 
==64986== 400 bytes in 1 blocks are definitely lost in loss record 1 of 1
==64986==    at 0x4C2B187: malloc (vg_replace_malloc.c:393)
==64986==    by 0x400545: main (data.c:8)
==64986== 
==64986== LEAK SUMMARY:
==64986==    definitely lost: 400 bytes in 1 blocks
==64986==    indirectly lost: 0 bytes in 0 blocks
==64986==      possibly lost: 0 bytes in 0 blocks
==64986==    still reachable: 0 bytes in 0 blocks
==64986==         suppressed: 0 bytes in 0 blocks
==64986== 
==64986== For lists of detected and suppressed errors, rerun with: -s
==64986== ERROR SUMMARY: 2 errors from 2 contexts (suppressed: 0 from 0)
```

**6．创建一个分配整数数组的程序（如上所述），释放它们，然后尝试打印数组中某个元素的值。程序会运行吗？当你使用 valgrind 时会发生什么？**

```c
#include <stdio.h>
#include <stdlib.h>
#include <unistd.h>

int
main(int argc, char *argv[])
{
    int* data = malloc(sizeof(int)*100);
    free(data);
    printf("index:0 value:%d", data[0]);
    return 0;
}
```

```sh
index:0 value:0[Inferior 1 (process 65172) exited normally]
```

非法读取

```sh
 valgrind --leak-check=yes ./data
==65225== Memcheck, a memory error detector
==65225== Copyright (C) 2002-2022, and GNU GPL'd, by Julian Seward et al.
==65225== Using Valgrind-3.20.0 and LibVEX; rerun with -h for copyright info
==65225== Command: ./data
==65225== 
==65225== Invalid read of size 4
==65225==    at 0x4005EA: main (data.c:10)
==65225==  Address 0x520a040 is 0 bytes inside a block of size 400 free'd
==65225==    at 0x4C2D70D: free (vg_replace_malloc.c:884)
==65225==    by 0x4005E5: main (data.c:9)
==65225==  Block was alloc'd at
==65225==    at 0x4C2B187: malloc (vg_replace_malloc.c:393)
==65225==    by 0x4005D5: main (data.c:8)
==65225== 
index:0 value:0==65225== 
==65225== HEAP SUMMARY:
==65225==     in use at exit: 0 bytes in 0 blocks
==65225==   total heap usage: 1 allocs, 1 frees, 400 bytes allocated
==65225== 
==65225== All heap blocks were freed -- no leaks are possible
==65225== 
==65225== For lists of detected and suppressed errors, rerun with: -s
==65225== ERROR SUMMARY: 1 errors from 1 contexts (suppressed: 0 from 0)
```

**7．现在传递一个有趣的值来释放（例如，在上面分配的数组中间的一个指针）。 会发生什么？你是否需要工具来找到这种类型的问题？**

 definitely lost: 400 bytes in 1 blocks

```c
#include <stdio.h>
#include <stdlib.h>
#include <unistd.h>

int
main(int argc, char *argv[])
{
    int* data = malloc(sizeof(int) * 100);
    free(&data[1]);
    printf("index:1 value:%d", data[1]);
    return 0;
}
```

```sh
00400000-00401000 r-xp 00000000 08:03 38182569                           /root/OSTEP/memony-api/hw/data
00600000-00601000 r--p 00000000 08:03 38182569                           /root/OSTEP/memony-api/hw/data
00601000-00602000 rw-p 00001000 08:03 38182569                           /root/OSTEP/memony-api/hw/data
0153c000-0155d000 rw-p 00000000 00:00 0                                  [heap]
7fc868000000-7fc868021000 rw-p 00000000 00:00 0 
7fc868021000-7fc86c000000 ---p 00000000 00:00 0 
7fc86f190000-7fc86f1a5000 r-xp 00000000 08:03 85                         /usr/lib64/libgcc_s-4.8.5-20150702.so.1
7fc86f1a5000-7fc86f3a4000 ---p 00015000 08:03 85                         /usr/lib64/libgcc_s-4.8.5-20150702.so.1
7fc86f3a4000-7fc86f3a5000 r--p 00014000 08:03 85                         /usr/lib64/libgcc_s-4.8.5-20150702.so.1
7fc86f3a5000-7fc86f3a6000 rw-p 00015000 08:03 85                         /usr/lib64/libgcc_s-4.8.5-20150702.so.1
7fc86f3a6000-7fc86f56a000 r-xp 00000000 08:03 373148                     /usr/lib64/libc-2.17.so
7fc86f56a000-7fc86f769000 ---p 001c4000 08:03 373148                     /usr/lib64/libc-2.17.so
7fc86f769000-7fc86f76d000 r--p 001c3000 08:03 373148                     /usr/lib64/libc-2.17.so
7fc86f76d000-7fc86f76f000 rw-p 001c7000 08:03 373148                     /usr/lib64/libc-2.17.so
7fc86f76f000-7fc86f774000 rw-p 00000000 00:00 0 
7fc86f774000-7fc86f796000 r-xp 00000000 08:03 373141                     /usr/lib64/ld-2.17.so
7fc86f97c000-7fc86f97f000 rw-p 00000000 00:00 0 
7fc86f993000-7fc86f995000 rw-p 00000000 00:00 0 
7fc86f995000-7fc86f996000 r--p 00021000 08:03 373141                     /usr/lib64/ld-2.17.so
7fc86f996000-7fc86f997000 rw-p 00022000 08:03 373141                     /usr/lib64/ld-2.17.so
7fc86f997000-7fc86f998000 rw-p 00000000 00:00 0 
7ffc34df0000-7ffc34e11000 rw-p 00000000 00:00 0                          [stack]
7ffc34e42000-7ffc34e44000 r-xp 00000000 00:00 0                          [vdso]
ffffffffff600000-ffffffffff601000 r-xp 00000000 00:00 0                  [vsyscall]
Aborted (core dumped)
```



```sh
valgrind --leak-check=yes ./data
==65518== Memcheck, a memory error detector
==65518== Copyright (C) 2002-2022, and GNU GPL'd, by Julian Seward et al.
==65518== Using Valgrind-3.20.0 and LibVEX; rerun with -h for copyright info
==65518== Command: ./data
==65518== 
==65518== Invalid free() / delete / delete[] / realloc()
==65518==    at 0x4C2D70D: free (vg_replace_malloc.c:884)
==65518==    by 0x4005E9: main (data.c:9)
==65518==  Address 0x520a044 is 4 bytes inside a block of size 400 alloc'd
==65518==    at 0x4C2B187: malloc (vg_replace_malloc.c:393)
==65518==    by 0x4005D5: main (data.c:8)
==65518== 
==65518== Conditional jump or move depends on uninitialised value(s)
==65518==    at 0x4E86C5E: vfprintf (in /usr/lib64/libc-2.17.so)
==65518==    by 0x4E8F4A8: printf (in /usr/lib64/libc-2.17.so)
==65518==    by 0x400604: main (data.c:10)
==65518== 
==65518== Use of uninitialised value of size 8
==65518==    at 0x4E8432B: _itoa_word (in /usr/lib64/libc-2.17.so)
==65518==    by 0x4E885B0: vfprintf (in /usr/lib64/libc-2.17.so)
==65518==    by 0x4E8F4A8: printf (in /usr/lib64/libc-2.17.so)
==65518==    by 0x400604: main (data.c:10)
==65518== 
==65518== Conditional jump or move depends on uninitialised value(s)
==65518==    at 0x4E84335: _itoa_word (in /usr/lib64/libc-2.17.so)
==65518==    by 0x4E885B0: vfprintf (in /usr/lib64/libc-2.17.so)
==65518==    by 0x4E8F4A8: printf (in /usr/lib64/libc-2.17.so)
==65518==    by 0x400604: main (data.c:10)
==65518== 
==65518== Conditional jump or move depends on uninitialised value(s)
==65518==    at 0x4E885FF: vfprintf (in /usr/lib64/libc-2.17.so)
==65518==    by 0x4E8F4A8: printf (in /usr/lib64/libc-2.17.so)
==65518==    by 0x400604: main (data.c:10)
==65518== 
==65518== Conditional jump or move depends on uninitialised value(s)
==65518==    at 0x4E86D2B: vfprintf (in /usr/lib64/libc-2.17.so)
==65518==    by 0x4E8F4A8: printf (in /usr/lib64/libc-2.17.so)
==65518==    by 0x400604: main (data.c:10)
==65518== 
==65518== Conditional jump or move depends on uninitialised value(s)
==65518==    at 0x4E86DAE: vfprintf (in /usr/lib64/libc-2.17.so)
==65518==    by 0x4E8F4A8: printf (in /usr/lib64/libc-2.17.so)
==65518==    by 0x400604: main (data.c:10)
==65518== 
index:1 value:0==65518== 
==65518== HEAP SUMMARY:
==65518==     in use at exit: 400 bytes in 1 blocks
==65518==   total heap usage: 1 allocs, 1 frees, 400 bytes allocated
==65518== 
==65518== 400 bytes in 1 blocks are definitely lost in loss record 1 of 1
==65518==    at 0x4C2B187: malloc (vg_replace_malloc.c:393)
==65518==    by 0x4005D5: main (data.c:8)
==65518== 
==65518== LEAK SUMMARY:
==65518==    definitely lost: 400 bytes in 1 blocks
==65518==    indirectly lost: 0 bytes in 0 blocks
==65518==      possibly lost: 0 bytes in 0 blocks
==65518==    still reachable: 0 bytes in 0 blocks
==65518==         suppressed: 0 bytes in 0 blocks
==65518== 
==65518== Use --track-origins=yes to see where uninitialised values come from
==65518== For lists of detected and suppressed errors, rerun with: -s
==65518== ERROR SUMMARY: 8 errors from 8 contexts (suppressed: 0 from 0)
```

