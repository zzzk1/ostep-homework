**问题**
**1．先让我们用一个小地址空间来转换一些地址。这里有一组简单的参数和几个不同的**
**随机种子。你可以转换这些地址吗？**
**segmentation.py -a 128 -p 512 -b 0 -l 20 -B 512 -L 20 -s 0**
**segmentation.py -a 128 -p 512 -b 0 -l 20 -B 512 -L 20 -s 1**
**segmentation.py -a 128 -p 512 -b 0 -l 20 -B 512 -L 20 -s 2**

**2．现在，让我们看看是否理解了这个构建的小地址空间（使用上面问题的参数）。段 0**
**中最高的合法虚拟地址是什么？段 1 中最低的合法虚拟地址是什么？在整个地址空间中，**
**最低和最高的非法地址是什么？最后，如何运行带有-A 标志的 segmentation.py 来测试你是**
**否正确？**

19 122

```sh
./segmentation.py -a 128 -p 512 -b 0 -l 20 -B 512 -L 20 -s 2 -A
ARG seed 2
ARG address space size 128
ARG phys mem size 512

Segment register information:

  Segment 0 base  (grows positive) : 0x00000000 (decimal 0)
  Segment 0 limit                  : 20

  Segment 1 base  (grows negative) : 0x00000200 (decimal 512)
  Segment 1 limit                  : 20

Virtual Address Trace
  VA  0: 0x0000007a (decimal:  122) --> VALID in SEG1: 0x000001fa (decimal:  506)
  VA  1: 0x00000079 (decimal:  121) --> VALID in SEG1: 0x000001f9 (decimal:  505)
  VA  2: 0x00000007 (decimal:    7) --> VALID in SEG0: 0x00000007 (decimal:    7)
  VA  3: 0x0000000a (decimal:   10) --> VALID in SEG0: 0x0000000a (decimal:   10)
  VA  4: 0x0000006a (decimal:  106) --> SEGMENTATION VIOLATION (SEG1)
```

**3．假设我们在一个 128 字节的物理内存中有一个很小的 16 字节地址空间。你会设置**
**什么样的基址和界限，以便让模拟器为指定的地址流生成以下转换结果：有效，有效，违**
**规，违反，有效，有效？假设用以下参数：**
**segmentation.py -a 16 -p 128**
**-A 0,1,2,3,4,5,6,7,8,9,10,11,12,13,14,15**
**--b0 ? --l0 ? --b1 ? --l1 ?**

**4．假设我们想要生成一个问题，其中大约 90%的随机生成的虚拟地址是有效的（即不**
**产生段异常）。你应该如何配置模拟器来做到这一点？哪些参数很重要？**

```sh
[root@localhost vm-segmentation]# ./segmentation.py -a 100 -p 300 -b0 0 -l 9 -A 0,1,2,3,4,5,6,7,8,9,101 -c
ARG seed 0
ARG address space size 100
ARG phys mem size 300

Segment register information:

  Segment 0 base  (grows positive) : 0x00000000 (decimal 0)
  Segment 0 limit                  : 9

  Segment 1 base  (grows negative) : 0x00000111 (decimal 273)
  Segment 1 limit                  : 46

Virtual Address Trace
  VA  0: 0x00000000 (decimal:    0) --> VALID in SEG0: 0x00000000 (decimal:    0)
  VA  1: 0x00000001 (decimal:    1) --> VALID in SEG0: 0x00000001 (decimal:    1)
  VA  2: 0x00000002 (decimal:    2) --> VALID in SEG0: 0x00000002 (decimal:    2)
  VA  3: 0x00000003 (decimal:    3) --> VALID in SEG0: 0x00000003 (decimal:    3)
  VA  4: 0x00000004 (decimal:    4) --> VALID in SEG0: 0x00000004 (decimal:    4)
  VA  5: 0x00000005 (decimal:    5) --> VALID in SEG0: 0x00000005 (decimal:    5)
  VA  6: 0x00000006 (decimal:    6) --> VALID in SEG0: 0x00000006 (decimal:    6)
  VA  7: 0x00000007 (decimal:    7) --> VALID in SEG0: 0x00000007 (decimal:    7)
  VA  8: 0x00000008 (decimal:    8) --> VALID in SEG0: 0x00000008 (decimal:    8)
  VA  9: 0x00000009 (decimal:    9) --> SEGMENTATION VIOLATION (SEG0)
```

**5．你可以运行模拟器，使所有虚拟地址无效吗？怎么做到？**

```sh
./segmentation.py -a 100 -p 300 -b0 0 -l 1 -A 3,4,5,6,7,8,9,101 -c
ARG seed 0
ARG address space size 100
ARG phys mem size 300

Segment register information:

  Segment 0 base  (grows positive) : 0x00000000 (decimal 0)
  Segment 0 limit                  : 1

  Segment 1 base  (grows negative) : 0x00000111 (decimal 273)
  Segment 1 limit                  : 46

Virtual Address Trace
  VA  0: 0x00000003 (decimal:    3) --> SEGMENTATION VIOLATION (SEG0)
  VA  1: 0x00000004 (decimal:    4) --> SEGMENTATION VIOLATION (SEG0)
  VA  2: 0x00000005 (decimal:    5) --> SEGMENTATION VIOLATION (SEG0)
  VA  3: 0x00000006 (decimal:    6) --> SEGMENTATION VIOLATION (SEG0)
  VA  4: 0x00000007 (decimal:    7) --> SEGMENTATION VIOLATION (SEG0)
  VA  5: 0x00000008 (decimal:    8) --> SEGMENTATION VIOLATION (SEG0)
  VA  6: 0x00000009 (decimal:    9) --> SEGMENTATION VIOLATION (SEG0)
```

