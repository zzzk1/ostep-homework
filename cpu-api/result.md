问题

**1．编写一个调用 fork()的程序。谁调用 fork()之前，让主进程访问一个变量（例如 x） 并将其值设置为某个值（例如 100）。子进程中的变量有谁谁值？当子进程和父进程都改变x 的值谁，变量会发生什么？**

```c
int
main(int argc, char *argv[])
{
    int x = 100;
    printf("x in parent: %d\n", x);
    int rc = fork();
    if (rc < 0) {
        fprintf(stderr, "fork failed\n");
        exit(1);
    } else if (rc == 0) {
        printf("x in child: %d\n", x);
    }
    return 0;
}

```

```sh
x in parent: 100
x in child: 100
```

子进程可能与父进程公用栈.

```c
int
main(int argc, char *argv[])
{
    int x = 100;
    printf("x in parent: %d\n", x);
    int rc = fork();
    if (rc < 0) {
        fprintf(stderr, "fork failed\n");
        exit(1);
    } else if (rc == 0) {
        x = 2;
        printf("x in child: %d\n", x);
    } else {
        printf("x in parent: %d\n", x);
    }
    return 0;
}
```

```sh
x in parent: 100
x in child: 2
x in parent: 100
```

子进程并未直接与父进程共享栈,而是复制了一份.

**2．编写一个打开文件的程序（使用 open()系统调用），然后调用 fork()创建一个新进程。 子进程和父进程都可以访问 open()返回的文件描述符吗？当它们并发（即同时）写入文件时，会发生什么？**

```c
int
main(int argc, char *argv[])
{
    int fd = open("./qs1.c",O_RDWR+O_CREAT);
    int rc = fork();
    if (rc < 0) {
        fprintf(stderr, "fork failed\n");
        exit(1);
    } else if (rc == 0) {
        printf("i am child(%d), get fd: %d\n", (int) getpid(), fd);
    } else {
        printf("i am parent(%d), get fd: %d\n",(int) getpid(), fd);
    }
    return 0;
}
```

```sh
i am parent(15713), get fd: 5
i am child(15718), get fd: 5
```

可以同时访问文件描述符.

```c
int
main(int argc, char *argv[])
{
    char sentence[1000];
    FILE *fptr;
    fptr = fopen("write.txt", "w");
    int rc = fork();
    if (rc < 0) {
        fprintf(stderr, "fork failed\n");
        exit(1);
    } else if (rc == 0) {
        fprintf(fptr, "%s", "hello, i am child");
        printf("i am child(%d)\n", (int) getpid());
    } else {
        fprintf(fptr, "%s", "hello, i am parent");
        printf("i am parent(%d)\n",(int) getpid());
    }
    return 0;
}
```

```tex
hello, i am parent
hello, i am child
```

**3．使用 fork()编写另一个程序。子进程应打印“hello”，父进程应打印“goodbye”。你 应该尝试我保子进程始终先打印。你能否我谁父进程调用 wait()而做到这一点呢？**

**4．编写一个调用 fork()的程序，然后调用某种形式的 exec()来运行程序/bin/ls。看看是 否可以尝试 exec()的所有变体，包括 execl()、execle()、execlp()、execv()、execvp()和 execvP()。**

```c
#include <stdio.h>
#include <stdlib.h>
#include <unistd.h>

int
main(int argc, char *argv[])
{
    int rc = fork();
    if (rc < 0) {
        fprintf(stderr, "fork failed\n");
        exit(1);
    } else if (rc == 0) {
        printf("I am child (pid:%d)\n", (int) getpid());
        execl("/bin/ls", "ls", "./", (char*)0);
    } else {
        printf("I am parent of %d (pid:%d)\n",rc, (int) getpid());
    }
    return 0;
}
```

```sh
I am parent of 17176 (pid:17171)
I am child (pid:17176)
ps3  ps3.c  qs1  qs1.c  qs2  qs2.c  qs4  qs4.c  write.txt
```

```c
int
main(int argc, char *argv[])
{
    int rc = fork();
    if (rc < 0) {
        fprintf(stderr, "fork failed\n");
        exit(1);
    } else if (rc == 0) {
        printf("I am child (pid:%d)\n", (int) getpid());
        execv("/bin/ls", "ls");
    } else {
        printf("I am parent of %d (pid:%d)\n",rc, (int) getpid());
    }
    return 0;
}
```

```sh
I am parent of 17384 (pid:17379)
I am child (pid:17384)
```

**5．现在编写一个程序，在父进程中使用 wait()，等待子进程完成。wait()返回什么?如果你在子进程中使用 wait()会发生什么？**

```c
#include <stdio.h>
#include <stdlib.h>
#include <unistd.h>
#include <sys/wait.h>

int
main(int argc, char *argv[])
{
    int rc = fork();
    if (rc < 0) {
        fprintf(stderr, "fork failed\n");
        exit(1);
    } else if (rc == 0) {
        printf("hello, I am child (pid:%d)\n", (int) getpid());
	sleep(1);
    } else {
        int wc = wait(NULL);
        printf("hello, I am parent of %d (wc:%d) (pid:%d)\n",rc, wc, (int) getpid());
    }
    return 0;
}
```

```sh
hello, I am child (pid:17660)
hello, I am parent of 17660 (wc:17660) (pid:17655)
```

wait() 返回子进程的pid.

```c
#include <stdio.h>
#include <stdlib.h>
#include <unistd.h>
#include <sys/wait.h>

int
main(int argc, char *argv[])
{
    int rc = fork();
    if (rc < 0) {
        fprintf(stderr, "fork failed\n");
        exit(1);
    } else if (rc == 0) {
        int wc = wait(NULL);
        printf("hello, I am child (pid:%d) (wc:%d)\n", (int) getpid(), wc);
	sleep(1);
    } else {
        int wc = wait(NULL);
        printf("hello, I am parent of %d (wc:%d) (pid:%d)\n",rc, wc, (int) getpid());
    }
    return 0;
}
```

```sh
hello, I am child (pid:17809) (wc:-1)
hello, I am parent of 17809 (wc:17809) (pid:17804)
```

子进程等待一段时间后返回.

**6．对前一个程序稍作修改，这次使用 waitpid()而不是 wait()。什么时候 waitpid()会 有用？**

```c
int
main(int argc, char *argv[])
{
    int rc = fork();
    if (rc < 0) {
        fprintf(stderr, "fork failed\n");
        exit(1);
    } else if (rc == 0) {
        int wc = waitpid(-1, NULL,0);
        printf("hello, I am child (pid:%d) (wc:%d)\n", (int) getpid(), wc);
	sleep(1);
    } else {
        int wc = waitpid(1, NULL,0);
        printf("hello, I am parent(pid:%d) (wc:%d) \n", (int) getpid(), wc);
    }
    return 0;
}
```

```sh
hello, I am parent(pid:18567) (wc:-1) 
hello, I am child (pid:18572) (wc:-1)
```

pid小于1或者pid等于子进程pid时有用.

**7．编写一个创建子进程的程序，然后在子进程中关闭标准输出（STDOUT_FILENO）。 如果子进程在关闭描述符后调用 printf()打印输出，会发生什么？**

```c
#include <stdio.h>
#include <stdlib.h>
#include <unistd.h>
#include <sys/wait.h>

int
main(int argc, char *argv[])
{
    int rc = fork();
    if (rc < 0) {
        fprintf(stderr, "fork failed\n");
        exit(1);
    } else if (rc == 0) {
        close(STDOUT_FILENO);
        printf("i am child(%d)", (int)getpid());
    } else {
        printf("i am parent(%d)", (int)getpid());
    }
    return 0;
}
```

```sh
i am parent(18832)
```

子进程不打印消息.

**8．编写一个程序，创建两个子进程，并使用 pipe()系统调用，将一个子进程的标准输出连接到另一个子进程的标准输入。**

```c
#include <stdio.h>
#include <stdlib.h>
#include <unistd.h>
#include <sys/wait.h>

#define MSGSIZE 5
char* msgIn = "pong!";
int
main(int argc, char *argv[])
{
    char inbuf[MSGSIZE];
    int pip[2];
    int forkIn = fork();
    if (forkIn == 0) {
        sleep(1);
        printf("ping!\n");
        write(pip[1], msgIn, MSGSIZE);
    } else if (forkIn > 0) {
        waitpid(forkIn,NULL,0);
        int forkOut = fork();
        if (forkOut == 0) {
        read(pip[0], inbuf, MSGSIZE);
        printf("%s\n", inbuf);
    }
    return 0;
    }
}
```

```sh
ping!
pong!
```

