**问题**
**1．只用两个工作和两个队列运行几个随机生成的问题。针对每个工作计算 MLFQ 的执行记录。限制每项作业的长度并关闭 I/O，让你的生活更轻松。**

```sh
./mlfq.py -j 2 -n 2 -M 0 -c
Here is the list of inputs:
OPTIONS jobs 2
OPTIONS queues 2
OPTIONS allotments for queue  1 is   1
OPTIONS quantum length for queue  1 is  10
OPTIONS allotments for queue  0 is   1
OPTIONS quantum length for queue  0 is  10
OPTIONS boost 0
OPTIONS ioTime 5
OPTIONS stayAfterIO False
OPTIONS iobump False


For each job, three defining characteristics are given:
  startTime : at what time does the job enter the system
  runTime   : the total CPU time needed by the job to finish
  ioFreq    : every ioFreq time units, the job issues an I/O
              (the I/O takes ioTime units to complete)

Job List:
  Job  0: startTime   0 - runTime  84 - ioFreq   0
  Job  1: startTime   0 - runTime  42 - ioFreq   0


Execution Trace:

[ time 0 ] JOB BEGINS by JOB 0
[ time 0 ] JOB BEGINS by JOB 1
[ time 0 ] Run JOB 0 at PRIORITY 1 [ TICKS 9 ALLOT 1 TIME 83 (of 84) ]
[ time 1 ] Run JOB 0 at PRIORITY 1 [ TICKS 8 ALLOT 1 TIME 82 (of 84) ]
[ time 2 ] Run JOB 0 at PRIORITY 1 [ TICKS 7 ALLOT 1 TIME 81 (of 84) ]
[ time 3 ] Run JOB 0 at PRIORITY 1 [ TICKS 6 ALLOT 1 TIME 80 (of 84) ]
[ time 4 ] Run JOB 0 at PRIORITY 1 [ TICKS 5 ALLOT 1 TIME 79 (of 84) ]
[ time 5 ] Run JOB 0 at PRIORITY 1 [ TICKS 4 ALLOT 1 TIME 78 (of 84) ]
[ time 6 ] Run JOB 0 at PRIORITY 1 [ TICKS 3 ALLOT 1 TIME 77 (of 84) ]
[ time 7 ] Run JOB 0 at PRIORITY 1 [ TICKS 2 ALLOT 1 TIME 76 (of 84) ]
[ time 8 ] Run JOB 0 at PRIORITY 1 [ TICKS 1 ALLOT 1 TIME 75 (of 84) ]
[ time 9 ] Run JOB 0 at PRIORITY 1 [ TICKS 0 ALLOT 1 TIME 74 (of 84) ]
[ time 10 ] Run JOB 1 at PRIORITY 1 [ TICKS 9 ALLOT 1 TIME 41 (of 42) ]
[ time 11 ] Run JOB 1 at PRIORITY 1 [ TICKS 8 ALLOT 1 TIME 40 (of 42) ]
[ time 12 ] Run JOB 1 at PRIORITY 1 [ TICKS 7 ALLOT 1 TIME 39 (of 42) ]
[ time 13 ] Run JOB 1 at PRIORITY 1 [ TICKS 6 ALLOT 1 TIME 38 (of 42) ]
[ time 14 ] Run JOB 1 at PRIORITY 1 [ TICKS 5 ALLOT 1 TIME 37 (of 42) ]
[ time 15 ] Run JOB 1 at PRIORITY 1 [ TICKS 4 ALLOT 1 TIME 36 (of 42) ]
[ time 16 ] Run JOB 1 at PRIORITY 1 [ TICKS 3 ALLOT 1 TIME 35 (of 42) ]
[ time 17 ] Run JOB 1 at PRIORITY 1 [ TICKS 2 ALLOT 1 TIME 34 (of 42) ]
[ time 18 ] Run JOB 1 at PRIORITY 1 [ TICKS 1 ALLOT 1 TIME 33 (of 42) ]
[ time 19 ] Run JOB 1 at PRIORITY 1 [ TICKS 0 ALLOT 1 TIME 32 (of 42) ]
[ time 20 ] Run JOB 0 at PRIORITY 0 [ TICKS 9 ALLOT 1 TIME 73 (of 84) ]
[ time 21 ] Run JOB 0 at PRIORITY 0 [ TICKS 8 ALLOT 1 TIME 72 (of 84) ]
[ time 22 ] Run JOB 0 at PRIORITY 0 [ TICKS 7 ALLOT 1 TIME 71 (of 84) ]
[ time 23 ] Run JOB 0 at PRIORITY 0 [ TICKS 6 ALLOT 1 TIME 70 (of 84) ]
[ time 24 ] Run JOB 0 at PRIORITY 0 [ TICKS 5 ALLOT 1 TIME 69 (of 84) ]
[ time 25 ] Run JOB 0 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 68 (of 84) ]
[ time 26 ] Run JOB 0 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 67 (of 84) ]
[ time 27 ] Run JOB 0 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 66 (of 84) ]
[ time 28 ] Run JOB 0 at PRIORITY 0 [ TICKS 1 ALLOT 1 TIME 65 (of 84) ]
[ time 29 ] Run JOB 0 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 64 (of 84) ]
[ time 30 ] Run JOB 1 at PRIORITY 0 [ TICKS 9 ALLOT 1 TIME 31 (of 42) ]
[ time 31 ] Run JOB 1 at PRIORITY 0 [ TICKS 8 ALLOT 1 TIME 30 (of 42) ]
[ time 32 ] Run JOB 1 at PRIORITY 0 [ TICKS 7 ALLOT 1 TIME 29 (of 42) ]
[ time 33 ] Run JOB 1 at PRIORITY 0 [ TICKS 6 ALLOT 1 TIME 28 (of 42) ]
[ time 34 ] Run JOB 1 at PRIORITY 0 [ TICKS 5 ALLOT 1 TIME 27 (of 42) ]
[ time 35 ] Run JOB 1 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 26 (of 42) ]
[ time 36 ] Run JOB 1 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 25 (of 42) ]
[ time 37 ] Run JOB 1 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 24 (of 42) ]
[ time 38 ] Run JOB 1 at PRIORITY 0 [ TICKS 1 ALLOT 1 TIME 23 (of 42) ]
[ time 39 ] Run JOB 1 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 22 (of 42) ]
[ time 40 ] Run JOB 0 at PRIORITY 0 [ TICKS 9 ALLOT 1 TIME 63 (of 84) ]
[ time 41 ] Run JOB 0 at PRIORITY 0 [ TICKS 8 ALLOT 1 TIME 62 (of 84) ]
[ time 42 ] Run JOB 0 at PRIORITY 0 [ TICKS 7 ALLOT 1 TIME 61 (of 84) ]
[ time 43 ] Run JOB 0 at PRIORITY 0 [ TICKS 6 ALLOT 1 TIME 60 (of 84) ]
[ time 44 ] Run JOB 0 at PRIORITY 0 [ TICKS 5 ALLOT 1 TIME 59 (of 84) ]
[ time 45 ] Run JOB 0 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 58 (of 84) ]
[ time 46 ] Run JOB 0 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 57 (of 84) ]
[ time 47 ] Run JOB 0 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 56 (of 84) ]
[ time 48 ] Run JOB 0 at PRIORITY 0 [ TICKS 1 ALLOT 1 TIME 55 (of 84) ]
[ time 49 ] Run JOB 0 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 54 (of 84) ]
[ time 50 ] Run JOB 1 at PRIORITY 0 [ TICKS 9 ALLOT 1 TIME 21 (of 42) ]
[ time 51 ] Run JOB 1 at PRIORITY 0 [ TICKS 8 ALLOT 1 TIME 20 (of 42) ]
[ time 52 ] Run JOB 1 at PRIORITY 0 [ TICKS 7 ALLOT 1 TIME 19 (of 42) ]
[ time 53 ] Run JOB 1 at PRIORITY 0 [ TICKS 6 ALLOT 1 TIME 18 (of 42) ]
[ time 54 ] Run JOB 1 at PRIORITY 0 [ TICKS 5 ALLOT 1 TIME 17 (of 42) ]
[ time 55 ] Run JOB 1 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 16 (of 42) ]
[ time 56 ] Run JOB 1 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 15 (of 42) ]
[ time 57 ] Run JOB 1 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 14 (of 42) ]
[ time 58 ] Run JOB 1 at PRIORITY 0 [ TICKS 1 ALLOT 1 TIME 13 (of 42) ]
[ time 59 ] Run JOB 1 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 12 (of 42) ]
[ time 60 ] Run JOB 0 at PRIORITY 0 [ TICKS 9 ALLOT 1 TIME 53 (of 84) ]
[ time 61 ] Run JOB 0 at PRIORITY 0 [ TICKS 8 ALLOT 1 TIME 52 (of 84) ]
[ time 62 ] Run JOB 0 at PRIORITY 0 [ TICKS 7 ALLOT 1 TIME 51 (of 84) ]
[ time 63 ] Run JOB 0 at PRIORITY 0 [ TICKS 6 ALLOT 1 TIME 50 (of 84) ]
[ time 64 ] Run JOB 0 at PRIORITY 0 [ TICKS 5 ALLOT 1 TIME 49 (of 84) ]
[ time 65 ] Run JOB 0 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 48 (of 84) ]
[ time 66 ] Run JOB 0 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 47 (of 84) ]
[ time 67 ] Run JOB 0 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 46 (of 84) ]
[ time 68 ] Run JOB 0 at PRIORITY 0 [ TICKS 1 ALLOT 1 TIME 45 (of 84) ]
[ time 69 ] Run JOB 0 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 44 (of 84) ]
[ time 70 ] Run JOB 1 at PRIORITY 0 [ TICKS 9 ALLOT 1 TIME 11 (of 42) ]
[ time 71 ] Run JOB 1 at PRIORITY 0 [ TICKS 8 ALLOT 1 TIME 10 (of 42) ]
[ time 72 ] Run JOB 1 at PRIORITY 0 [ TICKS 7 ALLOT 1 TIME 9 (of 42) ]
[ time 73 ] Run JOB 1 at PRIORITY 0 [ TICKS 6 ALLOT 1 TIME 8 (of 42) ]
[ time 74 ] Run JOB 1 at PRIORITY 0 [ TICKS 5 ALLOT 1 TIME 7 (of 42) ]
[ time 75 ] Run JOB 1 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 6 (of 42) ]
[ time 76 ] Run JOB 1 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 5 (of 42) ]
[ time 77 ] Run JOB 1 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 4 (of 42) ]
[ time 78 ] Run JOB 1 at PRIORITY 0 [ TICKS 1 ALLOT 1 TIME 3 (of 42) ]
[ time 79 ] Run JOB 1 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 2 (of 42) ]
[ time 80 ] Run JOB 0 at PRIORITY 0 [ TICKS 9 ALLOT 1 TIME 43 (of 84) ]
[ time 81 ] Run JOB 0 at PRIORITY 0 [ TICKS 8 ALLOT 1 TIME 42 (of 84) ]
[ time 82 ] Run JOB 0 at PRIORITY 0 [ TICKS 7 ALLOT 1 TIME 41 (of 84) ]
[ time 83 ] Run JOB 0 at PRIORITY 0 [ TICKS 6 ALLOT 1 TIME 40 (of 84) ]
[ time 84 ] Run JOB 0 at PRIORITY 0 [ TICKS 5 ALLOT 1 TIME 39 (of 84) ]
[ time 85 ] Run JOB 0 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 38 (of 84) ]
[ time 86 ] Run JOB 0 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 37 (of 84) ]
[ time 87 ] Run JOB 0 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 36 (of 84) ]
[ time 88 ] Run JOB 0 at PRIORITY 0 [ TICKS 1 ALLOT 1 TIME 35 (of 84) ]
[ time 89 ] Run JOB 0 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 34 (of 84) ]
[ time 90 ] Run JOB 1 at PRIORITY 0 [ TICKS 9 ALLOT 1 TIME 1 (of 42) ]
[ time 91 ] Run JOB 1 at PRIORITY 0 [ TICKS 8 ALLOT 1 TIME 0 (of 42) ]
[ time 92 ] FINISHED JOB 1
[ time 92 ] Run JOB 0 at PRIORITY 0 [ TICKS 9 ALLOT 1 TIME 33 (of 84) ]
[ time 93 ] Run JOB 0 at PRIORITY 0 [ TICKS 8 ALLOT 1 TIME 32 (of 84) ]
[ time 94 ] Run JOB 0 at PRIORITY 0 [ TICKS 7 ALLOT 1 TIME 31 (of 84) ]
[ time 95 ] Run JOB 0 at PRIORITY 0 [ TICKS 6 ALLOT 1 TIME 30 (of 84) ]
[ time 96 ] Run JOB 0 at PRIORITY 0 [ TICKS 5 ALLOT 1 TIME 29 (of 84) ]
[ time 97 ] Run JOB 0 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 28 (of 84) ]
[ time 98 ] Run JOB 0 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 27 (of 84) ]
[ time 99 ] Run JOB 0 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 26 (of 84) ]
[ time 100 ] Run JOB 0 at PRIORITY 0 [ TICKS 1 ALLOT 1 TIME 25 (of 84) ]
[ time 101 ] Run JOB 0 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 24 (of 84) ]
[ time 102 ] Run JOB 0 at PRIORITY 0 [ TICKS 9 ALLOT 1 TIME 23 (of 84) ]
[ time 103 ] Run JOB 0 at PRIORITY 0 [ TICKS 8 ALLOT 1 TIME 22 (of 84) ]
[ time 104 ] Run JOB 0 at PRIORITY 0 [ TICKS 7 ALLOT 1 TIME 21 (of 84) ]
[ time 105 ] Run JOB 0 at PRIORITY 0 [ TICKS 6 ALLOT 1 TIME 20 (of 84) ]
[ time 106 ] Run JOB 0 at PRIORITY 0 [ TICKS 5 ALLOT 1 TIME 19 (of 84) ]
[ time 107 ] Run JOB 0 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 18 (of 84) ]
[ time 108 ] Run JOB 0 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 17 (of 84) ]
[ time 109 ] Run JOB 0 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 16 (of 84) ]
[ time 110 ] Run JOB 0 at PRIORITY 0 [ TICKS 1 ALLOT 1 TIME 15 (of 84) ]
[ time 111 ] Run JOB 0 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 14 (of 84) ]
[ time 112 ] Run JOB 0 at PRIORITY 0 [ TICKS 9 ALLOT 1 TIME 13 (of 84) ]
[ time 113 ] Run JOB 0 at PRIORITY 0 [ TICKS 8 ALLOT 1 TIME 12 (of 84) ]
[ time 114 ] Run JOB 0 at PRIORITY 0 [ TICKS 7 ALLOT 1 TIME 11 (of 84) ]
[ time 115 ] Run JOB 0 at PRIORITY 0 [ TICKS 6 ALLOT 1 TIME 10 (of 84) ]
[ time 116 ] Run JOB 0 at PRIORITY 0 [ TICKS 5 ALLOT 1 TIME 9 (of 84) ]
[ time 117 ] Run JOB 0 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 8 (of 84) ]
[ time 118 ] Run JOB 0 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 7 (of 84) ]
[ time 119 ] Run JOB 0 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 6 (of 84) ]
[ time 120 ] Run JOB 0 at PRIORITY 0 [ TICKS 1 ALLOT 1 TIME 5 (of 84) ]
[ time 121 ] Run JOB 0 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 4 (of 84) ]
[ time 122 ] Run JOB 0 at PRIORITY 0 [ TICKS 9 ALLOT 1 TIME 3 (of 84) ]
[ time 123 ] Run JOB 0 at PRIORITY 0 [ TICKS 8 ALLOT 1 TIME 2 (of 84) ]
[ time 124 ] Run JOB 0 at PRIORITY 0 [ TICKS 7 ALLOT 1 TIME 1 (of 84) ]
[ time 125 ] Run JOB 0 at PRIORITY 0 [ TICKS 6 ALLOT 1 TIME 0 (of 84) ]
[ time 126 ] FINISHED JOB 0

Final statistics:
  Job  0: startTime   0 - response   0 - turnaround 126
  Job  1: startTime   0 - response  10 - turnaround  92

  Avg  1: startTime n/a - response 5.00 - turnaround 109.00

```



###### **2．如何运行调度程序来重现本章中的每个实例？**

```
规则 1：如果 A 的优先级 > B 的优先级，运行 A（不运行 B。
规则 2：如果 A 的优先级 = B 的优先级，轮转运行A 和 B
规则 3：工作进入系统时，放在最高优先级（最上层队列）。
规则 4a：工作用完整个时间片后，降低其优先级（移入下一个队列）。
规则 4b：如果工作在其时间片以内主动释放 CPU，则优先级不变。
```

实例 1：单个长工作

```sh
./mlfq.py --jlist 0,30,0 -n 3 -q 10 -i 1 -c
Here is the list of inputs:
OPTIONS jobs 1
OPTIONS queues 3
OPTIONS allotments for queue  2 is   1
OPTIONS quantum length for queue  2 is  10
OPTIONS allotments for queue  1 is   1
OPTIONS quantum length for queue  1 is  10
OPTIONS allotments for queue  0 is   1
OPTIONS quantum length for queue  0 is  10
OPTIONS boost 0
OPTIONS ioTime 1
OPTIONS stayAfterIO False
OPTIONS iobump False


For each job, three defining characteristics are given:
  startTime : at what time does the job enter the system
  runTime   : the total CPU time needed by the job to finish
  ioFreq    : every ioFreq time units, the job issues an I/O
              (the I/O takes ioTime units to complete)

Job List:
  Job  0: startTime   0 - runTime  30 - ioFreq   0


Execution Trace:

[ time 0 ] JOB BEGINS by JOB 0
[ time 0 ] Run JOB 0 at PRIORITY 2 [ TICKS 9 ALLOT 1 TIME 29 (of 30) ]
[ time 1 ] Run JOB 0 at PRIORITY 2 [ TICKS 8 ALLOT 1 TIME 28 (of 30) ]
[ time 2 ] Run JOB 0 at PRIORITY 2 [ TICKS 7 ALLOT 1 TIME 27 (of 30) ]
[ time 3 ] Run JOB 0 at PRIORITY 2 [ TICKS 6 ALLOT 1 TIME 26 (of 30) ]
[ time 4 ] Run JOB 0 at PRIORITY 2 [ TICKS 5 ALLOT 1 TIME 25 (of 30) ]
[ time 5 ] Run JOB 0 at PRIORITY 2 [ TICKS 4 ALLOT 1 TIME 24 (of 30) ]
[ time 6 ] Run JOB 0 at PRIORITY 2 [ TICKS 3 ALLOT 1 TIME 23 (of 30) ]
[ time 7 ] Run JOB 0 at PRIORITY 2 [ TICKS 2 ALLOT 1 TIME 22 (of 30) ]
[ time 8 ] Run JOB 0 at PRIORITY 2 [ TICKS 1 ALLOT 1 TIME 21 (of 30) ]
[ time 9 ] Run JOB 0 at PRIORITY 2 [ TICKS 0 ALLOT 1 TIME 20 (of 30) ]
[ time 10 ] Run JOB 0 at PRIORITY 1 [ TICKS 9 ALLOT 1 TIME 19 (of 30) ]
[ time 11 ] Run JOB 0 at PRIORITY 1 [ TICKS 8 ALLOT 1 TIME 18 (of 30) ]
[ time 12 ] Run JOB 0 at PRIORITY 1 [ TICKS 7 ALLOT 1 TIME 17 (of 30) ]
[ time 13 ] Run JOB 0 at PRIORITY 1 [ TICKS 6 ALLOT 1 TIME 16 (of 30) ]
[ time 14 ] Run JOB 0 at PRIORITY 1 [ TICKS 5 ALLOT 1 TIME 15 (of 30) ]
[ time 15 ] Run JOB 0 at PRIORITY 1 [ TICKS 4 ALLOT 1 TIME 14 (of 30) ]
[ time 16 ] Run JOB 0 at PRIORITY 1 [ TICKS 3 ALLOT 1 TIME 13 (of 30) ]
[ time 17 ] Run JOB 0 at PRIORITY 1 [ TICKS 2 ALLOT 1 TIME 12 (of 30) ]
[ time 18 ] Run JOB 0 at PRIORITY 1 [ TICKS 1 ALLOT 1 TIME 11 (of 30) ]
[ time 19 ] Run JOB 0 at PRIORITY 1 [ TICKS 0 ALLOT 1 TIME 10 (of 30) ]
[ time 20 ] Run JOB 0 at PRIORITY 0 [ TICKS 9 ALLOT 1 TIME 9 (of 30) ]
[ time 21 ] Run JOB 0 at PRIORITY 0 [ TICKS 8 ALLOT 1 TIME 8 (of 30) ]
[ time 22 ] Run JOB 0 at PRIORITY 0 [ TICKS 7 ALLOT 1 TIME 7 (of 30) ]
[ time 23 ] Run JOB 0 at PRIORITY 0 [ TICKS 6 ALLOT 1 TIME 6 (of 30) ]
[ time 24 ] Run JOB 0 at PRIORITY 0 [ TICKS 5 ALLOT 1 TIME 5 (of 30) ]
[ time 25 ] Run JOB 0 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 4 (of 30) ]
[ time 26 ] Run JOB 0 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 3 (of 30) ]
[ time 27 ] Run JOB 0 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 2 (of 30) ]
[ time 28 ] Run JOB 0 at PRIORITY 0 [ TICKS 1 ALLOT 1 TIME 1 (of 30) ]
[ time 29 ] Run JOB 0 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 0 (of 30) ]
[ time 30 ] FINISHED JOB 0

Final statistics:
  Job  0: startTime   0 - response   0 - turnaround  30

  Avg  0: startTime n/a - response 0.00 - turnaround 30.00


```

实例 2：来了一个短工作

```sh
./mlfq.py --jlist 0,40,0:20,15,0 -n 5 -q 10 -i 1 -c
Here is the list of inputs:
OPTIONS jobs 2
OPTIONS queues 5
OPTIONS allotments for queue  4 is   1
OPTIONS quantum length for queue  4 is  10
OPTIONS allotments for queue  3 is   1
OPTIONS quantum length for queue  3 is  10
OPTIONS allotments for queue  2 is   1
OPTIONS quantum length for queue  2 is  10
OPTIONS allotments for queue  1 is   1
OPTIONS quantum length for queue  1 is  10
OPTIONS allotments for queue  0 is   1
OPTIONS quantum length for queue  0 is  10
OPTIONS boost 0
OPTIONS ioTime 1
OPTIONS stayAfterIO False
OPTIONS iobump False


For each job, three defining characteristics are given:
  startTime : at what time does the job enter the system
  runTime   : the total CPU time needed by the job to finish
  ioFreq    : every ioFreq time units, the job issues an I/O
              (the I/O takes ioTime units to complete)

Job List:
  Job  0: startTime   0 - runTime  40 - ioFreq   0
  Job  1: startTime  20 - runTime  15 - ioFreq   0


Execution Trace:

[ time 0 ] JOB BEGINS by JOB 0
[ time 0 ] Run JOB 0 at PRIORITY 4 [ TICKS 9 ALLOT 1 TIME 39 (of 40) ]
[ time 1 ] Run JOB 0 at PRIORITY 4 [ TICKS 8 ALLOT 1 TIME 38 (of 40) ]
[ time 2 ] Run JOB 0 at PRIORITY 4 [ TICKS 7 ALLOT 1 TIME 37 (of 40) ]
[ time 3 ] Run JOB 0 at PRIORITY 4 [ TICKS 6 ALLOT 1 TIME 36 (of 40) ]
[ time 4 ] Run JOB 0 at PRIORITY 4 [ TICKS 5 ALLOT 1 TIME 35 (of 40) ]
[ time 5 ] Run JOB 0 at PRIORITY 4 [ TICKS 4 ALLOT 1 TIME 34 (of 40) ]
[ time 6 ] Run JOB 0 at PRIORITY 4 [ TICKS 3 ALLOT 1 TIME 33 (of 40) ]
[ time 7 ] Run JOB 0 at PRIORITY 4 [ TICKS 2 ALLOT 1 TIME 32 (of 40) ]
[ time 8 ] Run JOB 0 at PRIORITY 4 [ TICKS 1 ALLOT 1 TIME 31 (of 40) ]
[ time 9 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 30 (of 40) ]
[ time 10 ] Run JOB 0 at PRIORITY 3 [ TICKS 9 ALLOT 1 TIME 29 (of 40) ]
[ time 11 ] Run JOB 0 at PRIORITY 3 [ TICKS 8 ALLOT 1 TIME 28 (of 40) ]
[ time 12 ] Run JOB 0 at PRIORITY 3 [ TICKS 7 ALLOT 1 TIME 27 (of 40) ]
[ time 13 ] Run JOB 0 at PRIORITY 3 [ TICKS 6 ALLOT 1 TIME 26 (of 40) ]
[ time 14 ] Run JOB 0 at PRIORITY 3 [ TICKS 5 ALLOT 1 TIME 25 (of 40) ]
[ time 15 ] Run JOB 0 at PRIORITY 3 [ TICKS 4 ALLOT 1 TIME 24 (of 40) ]
[ time 16 ] Run JOB 0 at PRIORITY 3 [ TICKS 3 ALLOT 1 TIME 23 (of 40) ]
[ time 17 ] Run JOB 0 at PRIORITY 3 [ TICKS 2 ALLOT 1 TIME 22 (of 40) ]
[ time 18 ] Run JOB 0 at PRIORITY 3 [ TICKS 1 ALLOT 1 TIME 21 (of 40) ]
[ time 19 ] Run JOB 0 at PRIORITY 3 [ TICKS 0 ALLOT 1 TIME 20 (of 40) ]
[ time 20 ] JOB BEGINS by JOB 1
[ time 20 ] Run JOB 1 at PRIORITY 4 [ TICKS 9 ALLOT 1 TIME 14 (of 15) ]
[ time 21 ] Run JOB 1 at PRIORITY 4 [ TICKS 8 ALLOT 1 TIME 13 (of 15) ]
[ time 22 ] Run JOB 1 at PRIORITY 4 [ TICKS 7 ALLOT 1 TIME 12 (of 15) ]
[ time 23 ] Run JOB 1 at PRIORITY 4 [ TICKS 6 ALLOT 1 TIME 11 (of 15) ]
[ time 24 ] Run JOB 1 at PRIORITY 4 [ TICKS 5 ALLOT 1 TIME 10 (of 15) ]
[ time 25 ] Run JOB 1 at PRIORITY 4 [ TICKS 4 ALLOT 1 TIME 9 (of 15) ]
[ time 26 ] Run JOB 1 at PRIORITY 4 [ TICKS 3 ALLOT 1 TIME 8 (of 15) ]
[ time 27 ] Run JOB 1 at PRIORITY 4 [ TICKS 2 ALLOT 1 TIME 7 (of 15) ]
[ time 28 ] Run JOB 1 at PRIORITY 4 [ TICKS 1 ALLOT 1 TIME 6 (of 15) ]
[ time 29 ] Run JOB 1 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 5 (of 15) ]
[ time 30 ] Run JOB 1 at PRIORITY 3 [ TICKS 9 ALLOT 1 TIME 4 (of 15) ]
[ time 31 ] Run JOB 1 at PRIORITY 3 [ TICKS 8 ALLOT 1 TIME 3 (of 15) ]
[ time 32 ] Run JOB 1 at PRIORITY 3 [ TICKS 7 ALLOT 1 TIME 2 (of 15) ]
[ time 33 ] Run JOB 1 at PRIORITY 3 [ TICKS 6 ALLOT 1 TIME 1 (of 15) ]
[ time 34 ] Run JOB 1 at PRIORITY 3 [ TICKS 5 ALLOT 1 TIME 0 (of 15) ]
[ time 35 ] FINISHED JOB 1
[ time 35 ] Run JOB 0 at PRIORITY 2 [ TICKS 9 ALLOT 1 TIME 19 (of 40) ]
[ time 36 ] Run JOB 0 at PRIORITY 2 [ TICKS 8 ALLOT 1 TIME 18 (of 40) ]
[ time 37 ] Run JOB 0 at PRIORITY 2 [ TICKS 7 ALLOT 1 TIME 17 (of 40) ]
[ time 38 ] Run JOB 0 at PRIORITY 2 [ TICKS 6 ALLOT 1 TIME 16 (of 40) ]
[ time 39 ] Run JOB 0 at PRIORITY 2 [ TICKS 5 ALLOT 1 TIME 15 (of 40) ]
[ time 40 ] Run JOB 0 at PRIORITY 2 [ TICKS 4 ALLOT 1 TIME 14 (of 40) ]
[ time 41 ] Run JOB 0 at PRIORITY 2 [ TICKS 3 ALLOT 1 TIME 13 (of 40) ]
[ time 42 ] Run JOB 0 at PRIORITY 2 [ TICKS 2 ALLOT 1 TIME 12 (of 40) ]
[ time 43 ] Run JOB 0 at PRIORITY 2 [ TICKS 1 ALLOT 1 TIME 11 (of 40) ]
[ time 44 ] Run JOB 0 at PRIORITY 2 [ TICKS 0 ALLOT 1 TIME 10 (of 40) ]
[ time 45 ] Run JOB 0 at PRIORITY 1 [ TICKS 9 ALLOT 1 TIME 9 (of 40) ]
[ time 46 ] Run JOB 0 at PRIORITY 1 [ TICKS 8 ALLOT 1 TIME 8 (of 40) ]
[ time 47 ] Run JOB 0 at PRIORITY 1 [ TICKS 7 ALLOT 1 TIME 7 (of 40) ]
[ time 48 ] Run JOB 0 at PRIORITY 1 [ TICKS 6 ALLOT 1 TIME 6 (of 40) ]
[ time 49 ] Run JOB 0 at PRIORITY 1 [ TICKS 5 ALLOT 1 TIME 5 (of 40) ]
[ time 50 ] Run JOB 0 at PRIORITY 1 [ TICKS 4 ALLOT 1 TIME 4 (of 40) ]
[ time 51 ] Run JOB 0 at PRIORITY 1 [ TICKS 3 ALLOT 1 TIME 3 (of 40) ]
[ time 52 ] Run JOB 0 at PRIORITY 1 [ TICKS 2 ALLOT 1 TIME 2 (of 40) ]
[ time 53 ] Run JOB 0 at PRIORITY 1 [ TICKS 1 ALLOT 1 TIME 1 (of 40) ]
[ time 54 ] Run JOB 0 at PRIORITY 1 [ TICKS 0 ALLOT 1 TIME 0 (of 40) ]
[ time 55 ] FINISHED JOB 0

```

实例 3：如果有 I/O 呢

```sh
./mlfq.py --jlist 0,20,0:5,10,0 -n 5 -q 5 -i 1 -S -c
Here is the list of inputs:
OPTIONS jobs 2
OPTIONS queues 5
OPTIONS allotments for queue  4 is   1
OPTIONS quantum length for queue  4 is   5
OPTIONS allotments for queue  3 is   1
OPTIONS quantum length for queue  3 is   5
OPTIONS allotments for queue  2 is   1
OPTIONS quantum length for queue  2 is   5
OPTIONS allotments for queue  1 is   1
OPTIONS quantum length for queue  1 is   5
OPTIONS allotments for queue  0 is   1
OPTIONS quantum length for queue  0 is   5
OPTIONS boost 0
OPTIONS ioTime 1
OPTIONS stayAfterIO True
OPTIONS iobump False


For each job, three defining characteristics are given:
  startTime : at what time does the job enter the system
  runTime   : the total CPU time needed by the job to finish
  ioFreq    : every ioFreq time units, the job issues an I/O
              (the I/O takes ioTime units to complete)

Job List:
  Job  0: startTime   0 - runTime  20 - ioFreq   0
  Job  1: startTime   5 - runTime  10 - ioFreq   0


Execution Trace:

[ time 0 ] JOB BEGINS by JOB 0
[ time 0 ] Run JOB 0 at PRIORITY 4 [ TICKS 4 ALLOT 1 TIME 19 (of 20) ]
[ time 1 ] Run JOB 0 at PRIORITY 4 [ TICKS 3 ALLOT 1 TIME 18 (of 20) ]
[ time 2 ] Run JOB 0 at PRIORITY 4 [ TICKS 2 ALLOT 1 TIME 17 (of 20) ]
[ time 3 ] Run JOB 0 at PRIORITY 4 [ TICKS 1 ALLOT 1 TIME 16 (of 20) ]
[ time 4 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 15 (of 20) ]
[ time 5 ] JOB BEGINS by JOB 1
[ time 5 ] Run JOB 1 at PRIORITY 4 [ TICKS 4 ALLOT 1 TIME 9 (of 10) ]
[ time 6 ] Run JOB 1 at PRIORITY 4 [ TICKS 3 ALLOT 1 TIME 8 (of 10) ]
[ time 7 ] Run JOB 1 at PRIORITY 4 [ TICKS 2 ALLOT 1 TIME 7 (of 10) ]
[ time 8 ] Run JOB 1 at PRIORITY 4 [ TICKS 1 ALLOT 1 TIME 6 (of 10) ]
[ time 9 ] Run JOB 1 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 5 (of 10) ]
[ time 10 ] Run JOB 0 at PRIORITY 3 [ TICKS 4 ALLOT 1 TIME 14 (of 20) ]
[ time 11 ] Run JOB 0 at PRIORITY 3 [ TICKS 3 ALLOT 1 TIME 13 (of 20) ]
[ time 12 ] Run JOB 0 at PRIORITY 3 [ TICKS 2 ALLOT 1 TIME 12 (of 20) ]
[ time 13 ] Run JOB 0 at PRIORITY 3 [ TICKS 1 ALLOT 1 TIME 11 (of 20) ]
[ time 14 ] Run JOB 0 at PRIORITY 3 [ TICKS 0 ALLOT 1 TIME 10 (of 20) ]
[ time 15 ] Run JOB 1 at PRIORITY 3 [ TICKS 4 ALLOT 1 TIME 4 (of 10) ]
[ time 16 ] Run JOB 1 at PRIORITY 3 [ TICKS 3 ALLOT 1 TIME 3 (of 10) ]
[ time 17 ] Run JOB 1 at PRIORITY 3 [ TICKS 2 ALLOT 1 TIME 2 (of 10) ]
[ time 18 ] Run JOB 1 at PRIORITY 3 [ TICKS 1 ALLOT 1 TIME 1 (of 10) ]
[ time 19 ] Run JOB 1 at PRIORITY 3 [ TICKS 0 ALLOT 1 TIME 0 (of 10) ]
[ time 20 ] FINISHED JOB 1
[ time 20 ] Run JOB 0 at PRIORITY 2 [ TICKS 4 ALLOT 1 TIME 9 (of 20) ]
[ time 21 ] Run JOB 0 at PRIORITY 2 [ TICKS 3 ALLOT 1 TIME 8 (of 20) ]
[ time 22 ] Run JOB 0 at PRIORITY 2 [ TICKS 2 ALLOT 1 TIME 7 (of 20) ]
[ time 23 ] Run JOB 0 at PRIORITY 2 [ TICKS 1 ALLOT 1 TIME 6 (of 20) ]
[ time 24 ] Run JOB 0 at PRIORITY 2 [ TICKS 0 ALLOT 1 TIME 5 (of 20) ]
[ time 25 ] Run JOB 0 at PRIORITY 1 [ TICKS 4 ALLOT 1 TIME 4 (of 20) ]
[ time 26 ] Run JOB 0 at PRIORITY 1 [ TICKS 3 ALLOT 1 TIME 3 (of 20) ]
[ time 27 ] Run JOB 0 at PRIORITY 1 [ TICKS 2 ALLOT 1 TIME 2 (of 20) ]
[ time 28 ] Run JOB 0 at PRIORITY 1 [ TICKS 1 ALLOT 1 TIME 1 (of 20) ]
[ time 29 ] Run JOB 0 at PRIORITY 1 [ TICKS 0 ALLOT 1 TIME 0 (of 20) ]
[ time 30 ] FINISHED JOB 0
```

```
规则 5：经过一段时间 S，就将系统中所有工作重新加入最高优先级队列。


```

巫毒常量（voo-doo constant）

```sh
 ./mlfq.py --jlist 0,50,0:5,10,10:10,10,10 -n 5 -q 5 -i 1 -S -B 1 -c
Here is the list of inputs:
OPTIONS jobs 3
OPTIONS queues 5
OPTIONS allotments for queue  4 is   1
OPTIONS quantum length for queue  4 is   5
OPTIONS allotments for queue  3 is   1
OPTIONS quantum length for queue  3 is   5
OPTIONS allotments for queue  2 is   1
OPTIONS quantum length for queue  2 is   5
OPTIONS allotments for queue  1 is   1
OPTIONS quantum length for queue  1 is   5
OPTIONS allotments for queue  0 is   1
OPTIONS quantum length for queue  0 is   5
OPTIONS boost 1
OPTIONS ioTime 1
OPTIONS stayAfterIO True
OPTIONS iobump False


For each job, three defining characteristics are given:
  startTime : at what time does the job enter the system
  runTime   : the total CPU time needed by the job to finish
  ioFreq    : every ioFreq time units, the job issues an I/O
              (the I/O takes ioTime units to complete)

Job List:
  Job  0: startTime   0 - runTime  50 - ioFreq   0
  Job  1: startTime   5 - runTime  10 - ioFreq  10
  Job  2: startTime  10 - runTime  10 - ioFreq  10


Execution Trace:

[ time 0 ] JOB BEGINS by JOB 0
[ time 0 ] Run JOB 0 at PRIORITY 4 [ TICKS 4 ALLOT 1 TIME 49 (of 50) ]
[ time 1 ] BOOST ( every 1 )
[ time 1 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 48 (of 50) ]
[ time 2 ] BOOST ( every 1 )
[ time 2 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 47 (of 50) ]
[ time 3 ] BOOST ( every 1 )
[ time 3 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 46 (of 50) ]
[ time 4 ] BOOST ( every 1 )
[ time 4 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 45 (of 50) ]
[ time 5 ] BOOST ( every 1 )
[ time 5 ] JOB BEGINS by JOB 1
[ time 5 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 44 (of 50) ]
[ time 6 ] BOOST ( every 1 )
[ time 6 ] Run JOB 1 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 9 (of 10) ]
[ time 7 ] BOOST ( every 1 )
[ time 7 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 43 (of 50) ]
[ time 8 ] BOOST ( every 1 )
[ time 8 ] Run JOB 1 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 8 (of 10) ]
[ time 9 ] BOOST ( every 1 )
[ time 9 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 42 (of 50) ]
[ time 10 ] BOOST ( every 1 )
[ time 10 ] JOB BEGINS by JOB 2
[ time 10 ] Run JOB 1 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 7 (of 10) ]
[ time 11 ] BOOST ( every 1 )
[ time 11 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 41 (of 50) ]
[ time 12 ] BOOST ( every 1 )
[ time 12 ] Run JOB 2 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 9 (of 10) ]
[ time 13 ] BOOST ( every 1 )
[ time 13 ] Run JOB 1 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 6 (of 10) ]
[ time 14 ] BOOST ( every 1 )
[ time 14 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 40 (of 50) ]
[ time 15 ] BOOST ( every 1 )
[ time 15 ] Run JOB 2 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 8 (of 10) ]
[ time 16 ] BOOST ( every 1 )
[ time 16 ] Run JOB 1 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 5 (of 10) ]
[ time 17 ] BOOST ( every 1 )
[ time 17 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 39 (of 50) ]
[ time 18 ] BOOST ( every 1 )
[ time 18 ] Run JOB 2 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 7 (of 10) ]
[ time 19 ] BOOST ( every 1 )
[ time 19 ] Run JOB 1 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 4 (of 10) ]
[ time 20 ] BOOST ( every 1 )
[ time 20 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 38 (of 50) ]
[ time 21 ] BOOST ( every 1 )
[ time 21 ] Run JOB 2 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 6 (of 10) ]
[ time 22 ] BOOST ( every 1 )
[ time 22 ] Run JOB 1 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 3 (of 10) ]
[ time 23 ] BOOST ( every 1 )
[ time 23 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 37 (of 50) ]
[ time 24 ] BOOST ( every 1 )
[ time 24 ] Run JOB 2 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 5 (of 10) ]
[ time 25 ] BOOST ( every 1 )
[ time 25 ] Run JOB 1 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 2 (of 10) ]
[ time 26 ] BOOST ( every 1 )
[ time 26 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 36 (of 50) ]
[ time 27 ] BOOST ( every 1 )
[ time 27 ] Run JOB 2 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 4 (of 10) ]
[ time 28 ] BOOST ( every 1 )
[ time 28 ] Run JOB 1 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 1 (of 10) ]
[ time 29 ] BOOST ( every 1 )
[ time 29 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 35 (of 50) ]
[ time 30 ] BOOST ( every 1 )
[ time 30 ] Run JOB 2 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 3 (of 10) ]
[ time 31 ] BOOST ( every 1 )
[ time 31 ] Run JOB 1 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 0 (of 10) ]
[ time 32 ] FINISHED JOB 1
[ time 32 ] BOOST ( every 1 )
[ time 32 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 34 (of 50) ]
[ time 33 ] BOOST ( every 1 )
[ time 33 ] Run JOB 2 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 2 (of 10) ]
[ time 34 ] BOOST ( every 1 )
[ time 34 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 33 (of 50) ]
[ time 35 ] BOOST ( every 1 )
[ time 35 ] Run JOB 2 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 1 (of 10) ]
[ time 36 ] BOOST ( every 1 )
[ time 36 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 32 (of 50) ]
[ time 37 ] BOOST ( every 1 )
[ time 37 ] Run JOB 2 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 0 (of 10) ]
[ time 38 ] FINISHED JOB 2
[ time 38 ] BOOST ( every 1 )
[ time 38 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 31 (of 50) ]
[ time 39 ] BOOST ( every 1 )
[ time 39 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 30 (of 50) ]
[ time 40 ] BOOST ( every 1 )
[ time 40 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 29 (of 50) ]
[ time 41 ] BOOST ( every 1 )
[ time 41 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 28 (of 50) ]
[ time 42 ] BOOST ( every 1 )
[ time 42 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 27 (of 50) ]
[ time 43 ] BOOST ( every 1 )
[ time 43 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 26 (of 50) ]
[ time 44 ] BOOST ( every 1 )
[ time 44 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 25 (of 50) ]
[ time 45 ] BOOST ( every 1 )
[ time 45 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 24 (of 50) ]
[ time 46 ] BOOST ( every 1 )
[ time 46 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 23 (of 50) ]
[ time 47 ] BOOST ( every 1 )
[ time 47 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 22 (of 50) ]
[ time 48 ] BOOST ( every 1 )
[ time 48 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 21 (of 50) ]
[ time 49 ] BOOST ( every 1 )
[ time 49 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 20 (of 50) ]
[ time 50 ] BOOST ( every 1 )
[ time 50 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 19 (of 50) ]
[ time 51 ] BOOST ( every 1 )
[ time 51 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 18 (of 50) ]
[ time 52 ] BOOST ( every 1 )
[ time 52 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 17 (of 50) ]
[ time 53 ] BOOST ( every 1 )
[ time 53 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 16 (of 50) ]
[ time 54 ] BOOST ( every 1 )
[ time 54 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 15 (of 50) ]
[ time 55 ] BOOST ( every 1 )
[ time 55 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 14 (of 50) ]
[ time 56 ] BOOST ( every 1 )
[ time 56 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 13 (of 50) ]
[ time 57 ] BOOST ( every 1 )
[ time 57 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 12 (of 50) ]
[ time 58 ] BOOST ( every 1 )
[ time 58 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 11 (of 50) ]
[ time 59 ] BOOST ( every 1 )
[ time 59 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 10 (of 50) ]
[ time 60 ] BOOST ( every 1 )
[ time 60 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 9 (of 50) ]
[ time 61 ] BOOST ( every 1 )
[ time 61 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 8 (of 50) ]
[ time 62 ] BOOST ( every 1 )
[ time 62 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 7 (of 50) ]
[ time 63 ] BOOST ( every 1 )
[ time 63 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 6 (of 50) ]
[ time 64 ] BOOST ( every 1 )
[ time 64 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 5 (of 50) ]
[ time 65 ] BOOST ( every 1 )
[ time 65 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 4 (of 50) ]
[ time 66 ] BOOST ( every 1 )
[ time 66 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 3 (of 50) ]
[ time 67 ] BOOST ( every 1 )
[ time 67 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 2 (of 50) ]
[ time 68 ] BOOST ( every 1 )
[ time 68 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 1 (of 50) ]
[ time 69 ] BOOST ( every 1 )
[ time 69 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 0 (of 50) ]
[ time 70 ] FINISHED JOB 0
```

```
规则 4：一旦工作用完了其在某一层中的时间配额（无论中间主动放弃了多少次
CPU），就降低其优先级（移入低一级队列）。
```

```sh
./mlfq.py --jlist 0,50,0:5,10,10:10,10,10 -n 5 -q 5 -i 1 -S -B 1 -m 2 -c
Here is the list of inputs:
OPTIONS jobs 3
OPTIONS queues 5
OPTIONS allotments for queue  4 is   1
OPTIONS quantum length for queue  4 is   5
OPTIONS allotments for queue  3 is   1
OPTIONS quantum length for queue  3 is   5
OPTIONS allotments for queue  2 is   1
OPTIONS quantum length for queue  2 is   5
OPTIONS allotments for queue  1 is   1
OPTIONS quantum length for queue  1 is   5
OPTIONS allotments for queue  0 is   1
OPTIONS quantum length for queue  0 is   5
OPTIONS boost 1
OPTIONS ioTime 1
OPTIONS stayAfterIO True
OPTIONS iobump False


For each job, three defining characteristics are given:
  startTime : at what time does the job enter the system
  runTime   : the total CPU time needed by the job to finish
  ioFreq    : every ioFreq time units, the job issues an I/O
              (the I/O takes ioTime units to complete)

Job List:
  Job  0: startTime   0 - runTime  50 - ioFreq   0
  Job  1: startTime   5 - runTime  10 - ioFreq  10
  Job  2: startTime  10 - runTime  10 - ioFreq  10


Execution Trace:

[ time 0 ] JOB BEGINS by JOB 0
[ time 0 ] Run JOB 0 at PRIORITY 4 [ TICKS 4 ALLOT 1 TIME 49 (of 50) ]
[ time 1 ] BOOST ( every 1 )
[ time 1 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 48 (of 50) ]
[ time 2 ] BOOST ( every 1 )
[ time 2 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 47 (of 50) ]
[ time 3 ] BOOST ( every 1 )
[ time 3 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 46 (of 50) ]
[ time 4 ] BOOST ( every 1 )
[ time 4 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 45 (of 50) ]
[ time 5 ] BOOST ( every 1 )
[ time 5 ] JOB BEGINS by JOB 1
[ time 5 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 44 (of 50) ]
[ time 6 ] BOOST ( every 1 )
[ time 6 ] Run JOB 1 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 9 (of 10) ]
[ time 7 ] BOOST ( every 1 )
[ time 7 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 43 (of 50) ]
[ time 8 ] BOOST ( every 1 )
[ time 8 ] Run JOB 1 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 8 (of 10) ]
[ time 9 ] BOOST ( every 1 )
[ time 9 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 42 (of 50) ]
[ time 10 ] BOOST ( every 1 )
[ time 10 ] JOB BEGINS by JOB 2
[ time 10 ] Run JOB 1 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 7 (of 10) ]
[ time 11 ] BOOST ( every 1 )
[ time 11 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 41 (of 50) ]
[ time 12 ] BOOST ( every 1 )
[ time 12 ] Run JOB 2 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 9 (of 10) ]
[ time 13 ] BOOST ( every 1 )
[ time 13 ] Run JOB 1 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 6 (of 10) ]
[ time 14 ] BOOST ( every 1 )
[ time 14 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 40 (of 50) ]
[ time 15 ] BOOST ( every 1 )
[ time 15 ] Run JOB 2 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 8 (of 10) ]
[ time 16 ] BOOST ( every 1 )
[ time 16 ] Run JOB 1 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 5 (of 10) ]
[ time 17 ] BOOST ( every 1 )
[ time 17 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 39 (of 50) ]
[ time 18 ] BOOST ( every 1 )
[ time 18 ] Run JOB 2 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 7 (of 10) ]
[ time 19 ] BOOST ( every 1 )
[ time 19 ] Run JOB 1 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 4 (of 10) ]
[ time 20 ] BOOST ( every 1 )
[ time 20 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 38 (of 50) ]
[ time 21 ] BOOST ( every 1 )
[ time 21 ] Run JOB 2 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 6 (of 10) ]
[ time 22 ] BOOST ( every 1 )
[ time 22 ] Run JOB 1 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 3 (of 10) ]
[ time 23 ] BOOST ( every 1 )
[ time 23 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 37 (of 50) ]
[ time 24 ] BOOST ( every 1 )
[ time 24 ] Run JOB 2 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 5 (of 10) ]
[ time 25 ] BOOST ( every 1 )
[ time 25 ] Run JOB 1 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 2 (of 10) ]
[ time 26 ] BOOST ( every 1 )
[ time 26 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 36 (of 50) ]
[ time 27 ] BOOST ( every 1 )
[ time 27 ] Run JOB 2 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 4 (of 10) ]
[ time 28 ] BOOST ( every 1 )
[ time 28 ] Run JOB 1 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 1 (of 10) ]
[ time 29 ] BOOST ( every 1 )
[ time 29 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 35 (of 50) ]
[ time 30 ] BOOST ( every 1 )
[ time 30 ] Run JOB 2 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 3 (of 10) ]
[ time 31 ] BOOST ( every 1 )
[ time 31 ] Run JOB 1 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 0 (of 10) ]
[ time 32 ] FINISHED JOB 1
[ time 32 ] BOOST ( every 1 )
[ time 32 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 34 (of 50) ]
[ time 33 ] BOOST ( every 1 )
[ time 33 ] Run JOB 2 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 2 (of 10) ]
[ time 34 ] BOOST ( every 1 )
[ time 34 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 33 (of 50) ]
[ time 35 ] BOOST ( every 1 )
[ time 35 ] Run JOB 2 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 1 (of 10) ]
[ time 36 ] BOOST ( every 1 )
[ time 36 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 32 (of 50) ]
[ time 37 ] BOOST ( every 1 )
[ time 37 ] Run JOB 2 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 0 (of 10) ]
[ time 38 ] FINISHED JOB 2
[ time 38 ] BOOST ( every 1 )
[ time 38 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 31 (of 50) ]
[ time 39 ] BOOST ( every 1 )
[ time 39 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 30 (of 50) ]
[ time 40 ] BOOST ( every 1 )
[ time 40 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 29 (of 50) ]
[ time 41 ] BOOST ( every 1 )
[ time 41 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 28 (of 50) ]
[ time 42 ] BOOST ( every 1 )
[ time 42 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 27 (of 50) ]
[ time 43 ] BOOST ( every 1 )
[ time 43 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 26 (of 50) ]
[ time 44 ] BOOST ( every 1 )
[ time 44 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 25 (of 50) ]
[ time 45 ] BOOST ( every 1 )
[ time 45 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 24 (of 50) ]
[ time 46 ] BOOST ( every 1 )
[ time 46 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 23 (of 50) ]
[ time 47 ] BOOST ( every 1 )
[ time 47 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 22 (of 50) ]
[ time 48 ] BOOST ( every 1 )
[ time 48 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 21 (of 50) ]
[ time 49 ] BOOST ( every 1 )
[ time 49 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 20 (of 50) ]
[ time 50 ] BOOST ( every 1 )
[ time 50 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 19 (of 50) ]
[ time 51 ] BOOST ( every 1 )
[ time 51 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 18 (of 50) ]
[ time 52 ] BOOST ( every 1 )
[ time 52 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 17 (of 50) ]
[ time 53 ] BOOST ( every 1 )
[ time 53 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 16 (of 50) ]
[ time 54 ] BOOST ( every 1 )
[ time 54 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 15 (of 50) ]
[ time 55 ] BOOST ( every 1 )
[ time 55 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 14 (of 50) ]
[ time 56 ] BOOST ( every 1 )
[ time 56 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 13 (of 50) ]
[ time 57 ] BOOST ( every 1 )
[ time 57 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 12 (of 50) ]
[ time 58 ] BOOST ( every 1 )
[ time 58 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 11 (of 50) ]
[ time 59 ] BOOST ( every 1 )
[ time 59 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 10 (of 50) ]
[ time 60 ] BOOST ( every 1 )
[ time 60 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 9 (of 50) ]
[ time 61 ] BOOST ( every 1 )
[ time 61 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 8 (of 50) ]
[ time 62 ] BOOST ( every 1 )
[ time 62 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 7 (of 50) ]
[ time 63 ] BOOST ( every 1 )
[ time 63 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 6 (of 50) ]
[ time 64 ] BOOST ( every 1 )
[ time 64 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 5 (of 50) ]
[ time 65 ] BOOST ( every 1 )
[ time 65 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 4 (of 50) ]
[ time 66 ] BOOST ( every 1 )
[ time 66 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 3 (of 50) ]
[ time 67 ] BOOST ( every 1 )
[ time 67 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 2 (of 50) ]
[ time 68 ] BOOST ( every 1 )
[ time 68 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 1 (of 50) ]
[ time 69 ] BOOST ( every 1 )
[ time 69 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 0 (of 50) ]
[ time 70 ] FINISHED JOB 0
```

**3．将如何配置调度程序参数，像轮转调度程序那样工作？**

**4．设计两个工作的负载和调度程序参数，以便一个工作利用较早的规则 4a 和 4b（用-S 标志打开）来“愚弄”调度程序，在特定的时间间隔内获得 99%的 CPU。**

```sh
./mlfq.py --jlist 0,200,99:50,200,0 -i 1 -n 5 -q 100 -S -c
Here is the list of inputs:
OPTIONS jobs 2
OPTIONS queues 5
OPTIONS allotments for queue  4 is   1
OPTIONS quantum length for queue  4 is 100
OPTIONS allotments for queue  3 is   1
OPTIONS quantum length for queue  3 is 100
OPTIONS allotments for queue  2 is   1
OPTIONS quantum length for queue  2 is 100
OPTIONS allotments for queue  1 is   1
OPTIONS quantum length for queue  1 is 100
OPTIONS allotments for queue  0 is   1
OPTIONS quantum length for queue  0 is 100
OPTIONS boost 0
OPTIONS ioTime 1
OPTIONS stayAfterIO True
OPTIONS iobump False


For each job, three defining characteristics are given:
  startTime : at what time does the job enter the system
  runTime   : the total CPU time needed by the job to finish
  ioFreq    : every ioFreq time units, the job issues an I/O
              (the I/O takes ioTime units to complete)

Job List:
  Job  0: startTime   0 - runTime 200 - ioFreq  99
  Job  1: startTime  50 - runTime 200 - ioFreq   0


Execution Trace:

[ time 0 ] JOB BEGINS by JOB 0
[ time 0 ] Run JOB 0 at PRIORITY 4 [ TICKS 99 ALLOT 1 TIME 199 (of 200) ]
[ time 1 ] Run JOB 0 at PRIORITY 4 [ TICKS 98 ALLOT 1 TIME 198 (of 200) ]
[ time 2 ] Run JOB 0 at PRIORITY 4 [ TICKS 97 ALLOT 1 TIME 197 (of 200) ]
[ time 3 ] Run JOB 0 at PRIORITY 4 [ TICKS 96 ALLOT 1 TIME 196 (of 200) ]
[ time 4 ] Run JOB 0 at PRIORITY 4 [ TICKS 95 ALLOT 1 TIME 195 (of 200) ]
[ time 5 ] Run JOB 0 at PRIORITY 4 [ TICKS 94 ALLOT 1 TIME 194 (of 200) ]
[ time 6 ] Run JOB 0 at PRIORITY 4 [ TICKS 93 ALLOT 1 TIME 193 (of 200) ]
[ time 7 ] Run JOB 0 at PRIORITY 4 [ TICKS 92 ALLOT 1 TIME 192 (of 200) ]
[ time 8 ] Run JOB 0 at PRIORITY 4 [ TICKS 91 ALLOT 1 TIME 191 (of 200) ]
[ time 9 ] Run JOB 0 at PRIORITY 4 [ TICKS 90 ALLOT 1 TIME 190 (of 200) ]
[ time 10 ] Run JOB 0 at PRIORITY 4 [ TICKS 89 ALLOT 1 TIME 189 (of 200) ]
[ time 11 ] Run JOB 0 at PRIORITY 4 [ TICKS 88 ALLOT 1 TIME 188 (of 200) ]
[ time 12 ] Run JOB 0 at PRIORITY 4 [ TICKS 87 ALLOT 1 TIME 187 (of 200) ]
[ time 13 ] Run JOB 0 at PRIORITY 4 [ TICKS 86 ALLOT 1 TIME 186 (of 200) ]
[ time 14 ] Run JOB 0 at PRIORITY 4 [ TICKS 85 ALLOT 1 TIME 185 (of 200) ]
[ time 15 ] Run JOB 0 at PRIORITY 4 [ TICKS 84 ALLOT 1 TIME 184 (of 200) ]
[ time 16 ] Run JOB 0 at PRIORITY 4 [ TICKS 83 ALLOT 1 TIME 183 (of 200) ]
[ time 17 ] Run JOB 0 at PRIORITY 4 [ TICKS 82 ALLOT 1 TIME 182 (of 200) ]
[ time 18 ] Run JOB 0 at PRIORITY 4 [ TICKS 81 ALLOT 1 TIME 181 (of 200) ]
[ time 19 ] Run JOB 0 at PRIORITY 4 [ TICKS 80 ALLOT 1 TIME 180 (of 200) ]
[ time 20 ] Run JOB 0 at PRIORITY 4 [ TICKS 79 ALLOT 1 TIME 179 (of 200) ]
[ time 21 ] Run JOB 0 at PRIORITY 4 [ TICKS 78 ALLOT 1 TIME 178 (of 200) ]
[ time 22 ] Run JOB 0 at PRIORITY 4 [ TICKS 77 ALLOT 1 TIME 177 (of 200) ]
[ time 23 ] Run JOB 0 at PRIORITY 4 [ TICKS 76 ALLOT 1 TIME 176 (of 200) ]
[ time 24 ] Run JOB 0 at PRIORITY 4 [ TICKS 75 ALLOT 1 TIME 175 (of 200) ]
[ time 25 ] Run JOB 0 at PRIORITY 4 [ TICKS 74 ALLOT 1 TIME 174 (of 200) ]
[ time 26 ] Run JOB 0 at PRIORITY 4 [ TICKS 73 ALLOT 1 TIME 173 (of 200) ]
[ time 27 ] Run JOB 0 at PRIORITY 4 [ TICKS 72 ALLOT 1 TIME 172 (of 200) ]
[ time 28 ] Run JOB 0 at PRIORITY 4 [ TICKS 71 ALLOT 1 TIME 171 (of 200) ]
[ time 29 ] Run JOB 0 at PRIORITY 4 [ TICKS 70 ALLOT 1 TIME 170 (of 200) ]
[ time 30 ] Run JOB 0 at PRIORITY 4 [ TICKS 69 ALLOT 1 TIME 169 (of 200) ]
[ time 31 ] Run JOB 0 at PRIORITY 4 [ TICKS 68 ALLOT 1 TIME 168 (of 200) ]
[ time 32 ] Run JOB 0 at PRIORITY 4 [ TICKS 67 ALLOT 1 TIME 167 (of 200) ]
[ time 33 ] Run JOB 0 at PRIORITY 4 [ TICKS 66 ALLOT 1 TIME 166 (of 200) ]
[ time 34 ] Run JOB 0 at PRIORITY 4 [ TICKS 65 ALLOT 1 TIME 165 (of 200) ]
[ time 35 ] Run JOB 0 at PRIORITY 4 [ TICKS 64 ALLOT 1 TIME 164 (of 200) ]
[ time 36 ] Run JOB 0 at PRIORITY 4 [ TICKS 63 ALLOT 1 TIME 163 (of 200) ]
[ time 37 ] Run JOB 0 at PRIORITY 4 [ TICKS 62 ALLOT 1 TIME 162 (of 200) ]
[ time 38 ] Run JOB 0 at PRIORITY 4 [ TICKS 61 ALLOT 1 TIME 161 (of 200) ]
[ time 39 ] Run JOB 0 at PRIORITY 4 [ TICKS 60 ALLOT 1 TIME 160 (of 200) ]
[ time 40 ] Run JOB 0 at PRIORITY 4 [ TICKS 59 ALLOT 1 TIME 159 (of 200) ]
[ time 41 ] Run JOB 0 at PRIORITY 4 [ TICKS 58 ALLOT 1 TIME 158 (of 200) ]
[ time 42 ] Run JOB 0 at PRIORITY 4 [ TICKS 57 ALLOT 1 TIME 157 (of 200) ]
[ time 43 ] Run JOB 0 at PRIORITY 4 [ TICKS 56 ALLOT 1 TIME 156 (of 200) ]
[ time 44 ] Run JOB 0 at PRIORITY 4 [ TICKS 55 ALLOT 1 TIME 155 (of 200) ]
[ time 45 ] Run JOB 0 at PRIORITY 4 [ TICKS 54 ALLOT 1 TIME 154 (of 200) ]
[ time 46 ] Run JOB 0 at PRIORITY 4 [ TICKS 53 ALLOT 1 TIME 153 (of 200) ]
[ time 47 ] Run JOB 0 at PRIORITY 4 [ TICKS 52 ALLOT 1 TIME 152 (of 200) ]
[ time 48 ] Run JOB 0 at PRIORITY 4 [ TICKS 51 ALLOT 1 TIME 151 (of 200) ]
[ time 49 ] Run JOB 0 at PRIORITY 4 [ TICKS 50 ALLOT 1 TIME 150 (of 200) ]
[ time 50 ] JOB BEGINS by JOB 1
[ time 50 ] Run JOB 0 at PRIORITY 4 [ TICKS 49 ALLOT 1 TIME 149 (of 200) ]
[ time 51 ] Run JOB 0 at PRIORITY 4 [ TICKS 48 ALLOT 1 TIME 148 (of 200) ]
[ time 52 ] Run JOB 0 at PRIORITY 4 [ TICKS 47 ALLOT 1 TIME 147 (of 200) ]
[ time 53 ] Run JOB 0 at PRIORITY 4 [ TICKS 46 ALLOT 1 TIME 146 (of 200) ]
[ time 54 ] Run JOB 0 at PRIORITY 4 [ TICKS 45 ALLOT 1 TIME 145 (of 200) ]
[ time 55 ] Run JOB 0 at PRIORITY 4 [ TICKS 44 ALLOT 1 TIME 144 (of 200) ]
[ time 56 ] Run JOB 0 at PRIORITY 4 [ TICKS 43 ALLOT 1 TIME 143 (of 200) ]
[ time 57 ] Run JOB 0 at PRIORITY 4 [ TICKS 42 ALLOT 1 TIME 142 (of 200) ]
[ time 58 ] Run JOB 0 at PRIORITY 4 [ TICKS 41 ALLOT 1 TIME 141 (of 200) ]
[ time 59 ] Run JOB 0 at PRIORITY 4 [ TICKS 40 ALLOT 1 TIME 140 (of 200) ]
[ time 60 ] Run JOB 0 at PRIORITY 4 [ TICKS 39 ALLOT 1 TIME 139 (of 200) ]
[ time 61 ] Run JOB 0 at PRIORITY 4 [ TICKS 38 ALLOT 1 TIME 138 (of 200) ]
[ time 62 ] Run JOB 0 at PRIORITY 4 [ TICKS 37 ALLOT 1 TIME 137 (of 200) ]
[ time 63 ] Run JOB 0 at PRIORITY 4 [ TICKS 36 ALLOT 1 TIME 136 (of 200) ]
[ time 64 ] Run JOB 0 at PRIORITY 4 [ TICKS 35 ALLOT 1 TIME 135 (of 200) ]
[ time 65 ] Run JOB 0 at PRIORITY 4 [ TICKS 34 ALLOT 1 TIME 134 (of 200) ]
[ time 66 ] Run JOB 0 at PRIORITY 4 [ TICKS 33 ALLOT 1 TIME 133 (of 200) ]
[ time 67 ] Run JOB 0 at PRIORITY 4 [ TICKS 32 ALLOT 1 TIME 132 (of 200) ]
[ time 68 ] Run JOB 0 at PRIORITY 4 [ TICKS 31 ALLOT 1 TIME 131 (of 200) ]
[ time 69 ] Run JOB 0 at PRIORITY 4 [ TICKS 30 ALLOT 1 TIME 130 (of 200) ]
[ time 70 ] Run JOB 0 at PRIORITY 4 [ TICKS 29 ALLOT 1 TIME 129 (of 200) ]
[ time 71 ] Run JOB 0 at PRIORITY 4 [ TICKS 28 ALLOT 1 TIME 128 (of 200) ]
[ time 72 ] Run JOB 0 at PRIORITY 4 [ TICKS 27 ALLOT 1 TIME 127 (of 200) ]
[ time 73 ] Run JOB 0 at PRIORITY 4 [ TICKS 26 ALLOT 1 TIME 126 (of 200) ]
[ time 74 ] Run JOB 0 at PRIORITY 4 [ TICKS 25 ALLOT 1 TIME 125 (of 200) ]
[ time 75 ] Run JOB 0 at PRIORITY 4 [ TICKS 24 ALLOT 1 TIME 124 (of 200) ]
[ time 76 ] Run JOB 0 at PRIORITY 4 [ TICKS 23 ALLOT 1 TIME 123 (of 200) ]
[ time 77 ] Run JOB 0 at PRIORITY 4 [ TICKS 22 ALLOT 1 TIME 122 (of 200) ]
[ time 78 ] Run JOB 0 at PRIORITY 4 [ TICKS 21 ALLOT 1 TIME 121 (of 200) ]
[ time 79 ] Run JOB 0 at PRIORITY 4 [ TICKS 20 ALLOT 1 TIME 120 (of 200) ]
[ time 80 ] Run JOB 0 at PRIORITY 4 [ TICKS 19 ALLOT 1 TIME 119 (of 200) ]
[ time 81 ] Run JOB 0 at PRIORITY 4 [ TICKS 18 ALLOT 1 TIME 118 (of 200) ]
[ time 82 ] Run JOB 0 at PRIORITY 4 [ TICKS 17 ALLOT 1 TIME 117 (of 200) ]
[ time 83 ] Run JOB 0 at PRIORITY 4 [ TICKS 16 ALLOT 1 TIME 116 (of 200) ]
[ time 84 ] Run JOB 0 at PRIORITY 4 [ TICKS 15 ALLOT 1 TIME 115 (of 200) ]
[ time 85 ] Run JOB 0 at PRIORITY 4 [ TICKS 14 ALLOT 1 TIME 114 (of 200) ]
[ time 86 ] Run JOB 0 at PRIORITY 4 [ TICKS 13 ALLOT 1 TIME 113 (of 200) ]
[ time 87 ] Run JOB 0 at PRIORITY 4 [ TICKS 12 ALLOT 1 TIME 112 (of 200) ]
[ time 88 ] Run JOB 0 at PRIORITY 4 [ TICKS 11 ALLOT 1 TIME 111 (of 200) ]
[ time 89 ] Run JOB 0 at PRIORITY 4 [ TICKS 10 ALLOT 1 TIME 110 (of 200) ]
[ time 90 ] Run JOB 0 at PRIORITY 4 [ TICKS 9 ALLOT 1 TIME 109 (of 200) ]
[ time 91 ] Run JOB 0 at PRIORITY 4 [ TICKS 8 ALLOT 1 TIME 108 (of 200) ]
[ time 92 ] Run JOB 0 at PRIORITY 4 [ TICKS 7 ALLOT 1 TIME 107 (of 200) ]
[ time 93 ] Run JOB 0 at PRIORITY 4 [ TICKS 6 ALLOT 1 TIME 106 (of 200) ]
[ time 94 ] Run JOB 0 at PRIORITY 4 [ TICKS 5 ALLOT 1 TIME 105 (of 200) ]
[ time 95 ] Run JOB 0 at PRIORITY 4 [ TICKS 4 ALLOT 1 TIME 104 (of 200) ]
[ time 96 ] Run JOB 0 at PRIORITY 4 [ TICKS 3 ALLOT 1 TIME 103 (of 200) ]
[ time 97 ] Run JOB 0 at PRIORITY 4 [ TICKS 2 ALLOT 1 TIME 102 (of 200) ]
[ time 98 ] Run JOB 0 at PRIORITY 4 [ TICKS 1 ALLOT 1 TIME 101 (of 200) ]
[ time 99 ] IO_START by JOB 0
IO DONE
[ time 99 ] Run JOB 1 at PRIORITY 4 [ TICKS 99 ALLOT 1 TIME 199 (of 200) ]
[ time 100 ] IO_DONE by JOB 0
[ time 100 ] Run JOB 1 at PRIORITY 4 [ TICKS 98 ALLOT 1 TIME 198 (of 200) ]
[ time 101 ] Run JOB 1 at PRIORITY 4 [ TICKS 97 ALLOT 1 TIME 197 (of 200) ]
[ time 102 ] Run JOB 1 at PRIORITY 4 [ TICKS 96 ALLOT 1 TIME 196 (of 200) ]
[ time 103 ] Run JOB 1 at PRIORITY 4 [ TICKS 95 ALLOT 1 TIME 195 (of 200) ]
[ time 104 ] Run JOB 1 at PRIORITY 4 [ TICKS 94 ALLOT 1 TIME 194 (of 200) ]
[ time 105 ] Run JOB 1 at PRIORITY 4 [ TICKS 93 ALLOT 1 TIME 193 (of 200) ]
[ time 106 ] Run JOB 1 at PRIORITY 4 [ TICKS 92 ALLOT 1 TIME 192 (of 200) ]
[ time 107 ] Run JOB 1 at PRIORITY 4 [ TICKS 91 ALLOT 1 TIME 191 (of 200) ]
[ time 108 ] Run JOB 1 at PRIORITY 4 [ TICKS 90 ALLOT 1 TIME 190 (of 200) ]
[ time 109 ] Run JOB 1 at PRIORITY 4 [ TICKS 89 ALLOT 1 TIME 189 (of 200) ]
[ time 110 ] Run JOB 1 at PRIORITY 4 [ TICKS 88 ALLOT 1 TIME 188 (of 200) ]
[ time 111 ] Run JOB 1 at PRIORITY 4 [ TICKS 87 ALLOT 1 TIME 187 (of 200) ]
[ time 112 ] Run JOB 1 at PRIORITY 4 [ TICKS 86 ALLOT 1 TIME 186 (of 200) ]
[ time 113 ] Run JOB 1 at PRIORITY 4 [ TICKS 85 ALLOT 1 TIME 185 (of 200) ]
[ time 114 ] Run JOB 1 at PRIORITY 4 [ TICKS 84 ALLOT 1 TIME 184 (of 200) ]
[ time 115 ] Run JOB 1 at PRIORITY 4 [ TICKS 83 ALLOT 1 TIME 183 (of 200) ]
[ time 116 ] Run JOB 1 at PRIORITY 4 [ TICKS 82 ALLOT 1 TIME 182 (of 200) ]
[ time 117 ] Run JOB 1 at PRIORITY 4 [ TICKS 81 ALLOT 1 TIME 181 (of 200) ]
[ time 118 ] Run JOB 1 at PRIORITY 4 [ TICKS 80 ALLOT 1 TIME 180 (of 200) ]
[ time 119 ] Run JOB 1 at PRIORITY 4 [ TICKS 79 ALLOT 1 TIME 179 (of 200) ]
[ time 120 ] Run JOB 1 at PRIORITY 4 [ TICKS 78 ALLOT 1 TIME 178 (of 200) ]
[ time 121 ] Run JOB 1 at PRIORITY 4 [ TICKS 77 ALLOT 1 TIME 177 (of 200) ]
[ time 122 ] Run JOB 1 at PRIORITY 4 [ TICKS 76 ALLOT 1 TIME 176 (of 200) ]
[ time 123 ] Run JOB 1 at PRIORITY 4 [ TICKS 75 ALLOT 1 TIME 175 (of 200) ]
[ time 124 ] Run JOB 1 at PRIORITY 4 [ TICKS 74 ALLOT 1 TIME 174 (of 200) ]
[ time 125 ] Run JOB 1 at PRIORITY 4 [ TICKS 73 ALLOT 1 TIME 173 (of 200) ]
[ time 126 ] Run JOB 1 at PRIORITY 4 [ TICKS 72 ALLOT 1 TIME 172 (of 200) ]
[ time 127 ] Run JOB 1 at PRIORITY 4 [ TICKS 71 ALLOT 1 TIME 171 (of 200) ]
[ time 128 ] Run JOB 1 at PRIORITY 4 [ TICKS 70 ALLOT 1 TIME 170 (of 200) ]
[ time 129 ] Run JOB 1 at PRIORITY 4 [ TICKS 69 ALLOT 1 TIME 169 (of 200) ]
[ time 130 ] Run JOB 1 at PRIORITY 4 [ TICKS 68 ALLOT 1 TIME 168 (of 200) ]
[ time 131 ] Run JOB 1 at PRIORITY 4 [ TICKS 67 ALLOT 1 TIME 167 (of 200) ]
[ time 132 ] Run JOB 1 at PRIORITY 4 [ TICKS 66 ALLOT 1 TIME 166 (of 200) ]
[ time 133 ] Run JOB 1 at PRIORITY 4 [ TICKS 65 ALLOT 1 TIME 165 (of 200) ]
[ time 134 ] Run JOB 1 at PRIORITY 4 [ TICKS 64 ALLOT 1 TIME 164 (of 200) ]
[ time 135 ] Run JOB 1 at PRIORITY 4 [ TICKS 63 ALLOT 1 TIME 163 (of 200) ]
[ time 136 ] Run JOB 1 at PRIORITY 4 [ TICKS 62 ALLOT 1 TIME 162 (of 200) ]
[ time 137 ] Run JOB 1 at PRIORITY 4 [ TICKS 61 ALLOT 1 TIME 161 (of 200) ]
[ time 138 ] Run JOB 1 at PRIORITY 4 [ TICKS 60 ALLOT 1 TIME 160 (of 200) ]
[ time 139 ] Run JOB 1 at PRIORITY 4 [ TICKS 59 ALLOT 1 TIME 159 (of 200) ]
[ time 140 ] Run JOB 1 at PRIORITY 4 [ TICKS 58 ALLOT 1 TIME 158 (of 200) ]
[ time 141 ] Run JOB 1 at PRIORITY 4 [ TICKS 57 ALLOT 1 TIME 157 (of 200) ]
[ time 142 ] Run JOB 1 at PRIORITY 4 [ TICKS 56 ALLOT 1 TIME 156 (of 200) ]
[ time 143 ] Run JOB 1 at PRIORITY 4 [ TICKS 55 ALLOT 1 TIME 155 (of 200) ]
[ time 144 ] Run JOB 1 at PRIORITY 4 [ TICKS 54 ALLOT 1 TIME 154 (of 200) ]
[ time 145 ] Run JOB 1 at PRIORITY 4 [ TICKS 53 ALLOT 1 TIME 153 (of 200) ]
[ time 146 ] Run JOB 1 at PRIORITY 4 [ TICKS 52 ALLOT 1 TIME 152 (of 200) ]
[ time 147 ] Run JOB 1 at PRIORITY 4 [ TICKS 51 ALLOT 1 TIME 151 (of 200) ]
[ time 148 ] Run JOB 1 at PRIORITY 4 [ TICKS 50 ALLOT 1 TIME 150 (of 200) ]
[ time 149 ] Run JOB 1 at PRIORITY 4 [ TICKS 49 ALLOT 1 TIME 149 (of 200) ]
[ time 150 ] Run JOB 1 at PRIORITY 4 [ TICKS 48 ALLOT 1 TIME 148 (of 200) ]
[ time 151 ] Run JOB 1 at PRIORITY 4 [ TICKS 47 ALLOT 1 TIME 147 (of 200) ]
[ time 152 ] Run JOB 1 at PRIORITY 4 [ TICKS 46 ALLOT 1 TIME 146 (of 200) ]
[ time 153 ] Run JOB 1 at PRIORITY 4 [ TICKS 45 ALLOT 1 TIME 145 (of 200) ]
[ time 154 ] Run JOB 1 at PRIORITY 4 [ TICKS 44 ALLOT 1 TIME 144 (of 200) ]
[ time 155 ] Run JOB 1 at PRIORITY 4 [ TICKS 43 ALLOT 1 TIME 143 (of 200) ]
[ time 156 ] Run JOB 1 at PRIORITY 4 [ TICKS 42 ALLOT 1 TIME 142 (of 200) ]
[ time 157 ] Run JOB 1 at PRIORITY 4 [ TICKS 41 ALLOT 1 TIME 141 (of 200) ]
[ time 158 ] Run JOB 1 at PRIORITY 4 [ TICKS 40 ALLOT 1 TIME 140 (of 200) ]
[ time 159 ] Run JOB 1 at PRIORITY 4 [ TICKS 39 ALLOT 1 TIME 139 (of 200) ]
[ time 160 ] Run JOB 1 at PRIORITY 4 [ TICKS 38 ALLOT 1 TIME 138 (of 200) ]
[ time 161 ] Run JOB 1 at PRIORITY 4 [ TICKS 37 ALLOT 1 TIME 137 (of 200) ]
[ time 162 ] Run JOB 1 at PRIORITY 4 [ TICKS 36 ALLOT 1 TIME 136 (of 200) ]
[ time 163 ] Run JOB 1 at PRIORITY 4 [ TICKS 35 ALLOT 1 TIME 135 (of 200) ]
[ time 164 ] Run JOB 1 at PRIORITY 4 [ TICKS 34 ALLOT 1 TIME 134 (of 200) ]
[ time 165 ] Run JOB 1 at PRIORITY 4 [ TICKS 33 ALLOT 1 TIME 133 (of 200) ]
[ time 166 ] Run JOB 1 at PRIORITY 4 [ TICKS 32 ALLOT 1 TIME 132 (of 200) ]
[ time 167 ] Run JOB 1 at PRIORITY 4 [ TICKS 31 ALLOT 1 TIME 131 (of 200) ]
[ time 168 ] Run JOB 1 at PRIORITY 4 [ TICKS 30 ALLOT 1 TIME 130 (of 200) ]
[ time 169 ] Run JOB 1 at PRIORITY 4 [ TICKS 29 ALLOT 1 TIME 129 (of 200) ]
[ time 170 ] Run JOB 1 at PRIORITY 4 [ TICKS 28 ALLOT 1 TIME 128 (of 200) ]
[ time 171 ] Run JOB 1 at PRIORITY 4 [ TICKS 27 ALLOT 1 TIME 127 (of 200) ]
[ time 172 ] Run JOB 1 at PRIORITY 4 [ TICKS 26 ALLOT 1 TIME 126 (of 200) ]
[ time 173 ] Run JOB 1 at PRIORITY 4 [ TICKS 25 ALLOT 1 TIME 125 (of 200) ]
[ time 174 ] Run JOB 1 at PRIORITY 4 [ TICKS 24 ALLOT 1 TIME 124 (of 200) ]
[ time 175 ] Run JOB 1 at PRIORITY 4 [ TICKS 23 ALLOT 1 TIME 123 (of 200) ]
[ time 176 ] Run JOB 1 at PRIORITY 4 [ TICKS 22 ALLOT 1 TIME 122 (of 200) ]
[ time 177 ] Run JOB 1 at PRIORITY 4 [ TICKS 21 ALLOT 1 TIME 121 (of 200) ]
[ time 178 ] Run JOB 1 at PRIORITY 4 [ TICKS 20 ALLOT 1 TIME 120 (of 200) ]
[ time 179 ] Run JOB 1 at PRIORITY 4 [ TICKS 19 ALLOT 1 TIME 119 (of 200) ]
[ time 180 ] Run JOB 1 at PRIORITY 4 [ TICKS 18 ALLOT 1 TIME 118 (of 200) ]
[ time 181 ] Run JOB 1 at PRIORITY 4 [ TICKS 17 ALLOT 1 TIME 117 (of 200) ]
[ time 182 ] Run JOB 1 at PRIORITY 4 [ TICKS 16 ALLOT 1 TIME 116 (of 200) ]
[ time 183 ] Run JOB 1 at PRIORITY 4 [ TICKS 15 ALLOT 1 TIME 115 (of 200) ]
[ time 184 ] Run JOB 1 at PRIORITY 4 [ TICKS 14 ALLOT 1 TIME 114 (of 200) ]
[ time 185 ] Run JOB 1 at PRIORITY 4 [ TICKS 13 ALLOT 1 TIME 113 (of 200) ]
[ time 186 ] Run JOB 1 at PRIORITY 4 [ TICKS 12 ALLOT 1 TIME 112 (of 200) ]
[ time 187 ] Run JOB 1 at PRIORITY 4 [ TICKS 11 ALLOT 1 TIME 111 (of 200) ]
[ time 188 ] Run JOB 1 at PRIORITY 4 [ TICKS 10 ALLOT 1 TIME 110 (of 200) ]
[ time 189 ] Run JOB 1 at PRIORITY 4 [ TICKS 9 ALLOT 1 TIME 109 (of 200) ]
[ time 190 ] Run JOB 1 at PRIORITY 4 [ TICKS 8 ALLOT 1 TIME 108 (of 200) ]
[ time 191 ] Run JOB 1 at PRIORITY 4 [ TICKS 7 ALLOT 1 TIME 107 (of 200) ]
[ time 192 ] Run JOB 1 at PRIORITY 4 [ TICKS 6 ALLOT 1 TIME 106 (of 200) ]
[ time 193 ] Run JOB 1 at PRIORITY 4 [ TICKS 5 ALLOT 1 TIME 105 (of 200) ]
[ time 194 ] Run JOB 1 at PRIORITY 4 [ TICKS 4 ALLOT 1 TIME 104 (of 200) ]
[ time 195 ] Run JOB 1 at PRIORITY 4 [ TICKS 3 ALLOT 1 TIME 103 (of 200) ]
[ time 196 ] Run JOB 1 at PRIORITY 4 [ TICKS 2 ALLOT 1 TIME 102 (of 200) ]
[ time 197 ] Run JOB 1 at PRIORITY 4 [ TICKS 1 ALLOT 1 TIME 101 (of 200) ]
[ time 198 ] Run JOB 1 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 100 (of 200) ]
[ time 199 ] Run JOB 0 at PRIORITY 4 [ TICKS 99 ALLOT 1 TIME 100 (of 200) ]
[ time 200 ] Run JOB 0 at PRIORITY 4 [ TICKS 98 ALLOT 1 TIME 99 (of 200) ]
[ time 201 ] Run JOB 0 at PRIORITY 4 [ TICKS 97 ALLOT 1 TIME 98 (of 200) ]
[ time 202 ] Run JOB 0 at PRIORITY 4 [ TICKS 96 ALLOT 1 TIME 97 (of 200) ]
[ time 203 ] Run JOB 0 at PRIORITY 4 [ TICKS 95 ALLOT 1 TIME 96 (of 200) ]
[ time 204 ] Run JOB 0 at PRIORITY 4 [ TICKS 94 ALLOT 1 TIME 95 (of 200) ]
[ time 205 ] Run JOB 0 at PRIORITY 4 [ TICKS 93 ALLOT 1 TIME 94 (of 200) ]
[ time 206 ] Run JOB 0 at PRIORITY 4 [ TICKS 92 ALLOT 1 TIME 93 (of 200) ]
[ time 207 ] Run JOB 0 at PRIORITY 4 [ TICKS 91 ALLOT 1 TIME 92 (of 200) ]
[ time 208 ] Run JOB 0 at PRIORITY 4 [ TICKS 90 ALLOT 1 TIME 91 (of 200) ]
[ time 209 ] Run JOB 0 at PRIORITY 4 [ TICKS 89 ALLOT 1 TIME 90 (of 200) ]
[ time 210 ] Run JOB 0 at PRIORITY 4 [ TICKS 88 ALLOT 1 TIME 89 (of 200) ]
[ time 211 ] Run JOB 0 at PRIORITY 4 [ TICKS 87 ALLOT 1 TIME 88 (of 200) ]
[ time 212 ] Run JOB 0 at PRIORITY 4 [ TICKS 86 ALLOT 1 TIME 87 (of 200) ]
[ time 213 ] Run JOB 0 at PRIORITY 4 [ TICKS 85 ALLOT 1 TIME 86 (of 200) ]
[ time 214 ] Run JOB 0 at PRIORITY 4 [ TICKS 84 ALLOT 1 TIME 85 (of 200) ]
[ time 215 ] Run JOB 0 at PRIORITY 4 [ TICKS 83 ALLOT 1 TIME 84 (of 200) ]
[ time 216 ] Run JOB 0 at PRIORITY 4 [ TICKS 82 ALLOT 1 TIME 83 (of 200) ]
[ time 217 ] Run JOB 0 at PRIORITY 4 [ TICKS 81 ALLOT 1 TIME 82 (of 200) ]
[ time 218 ] Run JOB 0 at PRIORITY 4 [ TICKS 80 ALLOT 1 TIME 81 (of 200) ]
[ time 219 ] Run JOB 0 at PRIORITY 4 [ TICKS 79 ALLOT 1 TIME 80 (of 200) ]
[ time 220 ] Run JOB 0 at PRIORITY 4 [ TICKS 78 ALLOT 1 TIME 79 (of 200) ]
[ time 221 ] Run JOB 0 at PRIORITY 4 [ TICKS 77 ALLOT 1 TIME 78 (of 200) ]
[ time 222 ] Run JOB 0 at PRIORITY 4 [ TICKS 76 ALLOT 1 TIME 77 (of 200) ]
[ time 223 ] Run JOB 0 at PRIORITY 4 [ TICKS 75 ALLOT 1 TIME 76 (of 200) ]
[ time 224 ] Run JOB 0 at PRIORITY 4 [ TICKS 74 ALLOT 1 TIME 75 (of 200) ]
[ time 225 ] Run JOB 0 at PRIORITY 4 [ TICKS 73 ALLOT 1 TIME 74 (of 200) ]
[ time 226 ] Run JOB 0 at PRIORITY 4 [ TICKS 72 ALLOT 1 TIME 73 (of 200) ]
[ time 227 ] Run JOB 0 at PRIORITY 4 [ TICKS 71 ALLOT 1 TIME 72 (of 200) ]
[ time 228 ] Run JOB 0 at PRIORITY 4 [ TICKS 70 ALLOT 1 TIME 71 (of 200) ]
[ time 229 ] Run JOB 0 at PRIORITY 4 [ TICKS 69 ALLOT 1 TIME 70 (of 200) ]
[ time 230 ] Run JOB 0 at PRIORITY 4 [ TICKS 68 ALLOT 1 TIME 69 (of 200) ]
[ time 231 ] Run JOB 0 at PRIORITY 4 [ TICKS 67 ALLOT 1 TIME 68 (of 200) ]
[ time 232 ] Run JOB 0 at PRIORITY 4 [ TICKS 66 ALLOT 1 TIME 67 (of 200) ]
[ time 233 ] Run JOB 0 at PRIORITY 4 [ TICKS 65 ALLOT 1 TIME 66 (of 200) ]
[ time 234 ] Run JOB 0 at PRIORITY 4 [ TICKS 64 ALLOT 1 TIME 65 (of 200) ]
[ time 235 ] Run JOB 0 at PRIORITY 4 [ TICKS 63 ALLOT 1 TIME 64 (of 200) ]
[ time 236 ] Run JOB 0 at PRIORITY 4 [ TICKS 62 ALLOT 1 TIME 63 (of 200) ]
[ time 237 ] Run JOB 0 at PRIORITY 4 [ TICKS 61 ALLOT 1 TIME 62 (of 200) ]
[ time 238 ] Run JOB 0 at PRIORITY 4 [ TICKS 60 ALLOT 1 TIME 61 (of 200) ]
[ time 239 ] Run JOB 0 at PRIORITY 4 [ TICKS 59 ALLOT 1 TIME 60 (of 200) ]
[ time 240 ] Run JOB 0 at PRIORITY 4 [ TICKS 58 ALLOT 1 TIME 59 (of 200) ]
[ time 241 ] Run JOB 0 at PRIORITY 4 [ TICKS 57 ALLOT 1 TIME 58 (of 200) ]
[ time 242 ] Run JOB 0 at PRIORITY 4 [ TICKS 56 ALLOT 1 TIME 57 (of 200) ]
[ time 243 ] Run JOB 0 at PRIORITY 4 [ TICKS 55 ALLOT 1 TIME 56 (of 200) ]
[ time 244 ] Run JOB 0 at PRIORITY 4 [ TICKS 54 ALLOT 1 TIME 55 (of 200) ]
[ time 245 ] Run JOB 0 at PRIORITY 4 [ TICKS 53 ALLOT 1 TIME 54 (of 200) ]
[ time 246 ] Run JOB 0 at PRIORITY 4 [ TICKS 52 ALLOT 1 TIME 53 (of 200) ]
[ time 247 ] Run JOB 0 at PRIORITY 4 [ TICKS 51 ALLOT 1 TIME 52 (of 200) ]
[ time 248 ] Run JOB 0 at PRIORITY 4 [ TICKS 50 ALLOT 1 TIME 51 (of 200) ]
[ time 249 ] Run JOB 0 at PRIORITY 4 [ TICKS 49 ALLOT 1 TIME 50 (of 200) ]
[ time 250 ] Run JOB 0 at PRIORITY 4 [ TICKS 48 ALLOT 1 TIME 49 (of 200) ]
[ time 251 ] Run JOB 0 at PRIORITY 4 [ TICKS 47 ALLOT 1 TIME 48 (of 200) ]
[ time 252 ] Run JOB 0 at PRIORITY 4 [ TICKS 46 ALLOT 1 TIME 47 (of 200) ]
[ time 253 ] Run JOB 0 at PRIORITY 4 [ TICKS 45 ALLOT 1 TIME 46 (of 200) ]
[ time 254 ] Run JOB 0 at PRIORITY 4 [ TICKS 44 ALLOT 1 TIME 45 (of 200) ]
[ time 255 ] Run JOB 0 at PRIORITY 4 [ TICKS 43 ALLOT 1 TIME 44 (of 200) ]
[ time 256 ] Run JOB 0 at PRIORITY 4 [ TICKS 42 ALLOT 1 TIME 43 (of 200) ]
[ time 257 ] Run JOB 0 at PRIORITY 4 [ TICKS 41 ALLOT 1 TIME 42 (of 200) ]
[ time 258 ] Run JOB 0 at PRIORITY 4 [ TICKS 40 ALLOT 1 TIME 41 (of 200) ]
[ time 259 ] Run JOB 0 at PRIORITY 4 [ TICKS 39 ALLOT 1 TIME 40 (of 200) ]
[ time 260 ] Run JOB 0 at PRIORITY 4 [ TICKS 38 ALLOT 1 TIME 39 (of 200) ]
[ time 261 ] Run JOB 0 at PRIORITY 4 [ TICKS 37 ALLOT 1 TIME 38 (of 200) ]
[ time 262 ] Run JOB 0 at PRIORITY 4 [ TICKS 36 ALLOT 1 TIME 37 (of 200) ]
[ time 263 ] Run JOB 0 at PRIORITY 4 [ TICKS 35 ALLOT 1 TIME 36 (of 200) ]
[ time 264 ] Run JOB 0 at PRIORITY 4 [ TICKS 34 ALLOT 1 TIME 35 (of 200) ]
[ time 265 ] Run JOB 0 at PRIORITY 4 [ TICKS 33 ALLOT 1 TIME 34 (of 200) ]
[ time 266 ] Run JOB 0 at PRIORITY 4 [ TICKS 32 ALLOT 1 TIME 33 (of 200) ]
[ time 267 ] Run JOB 0 at PRIORITY 4 [ TICKS 31 ALLOT 1 TIME 32 (of 200) ]
[ time 268 ] Run JOB 0 at PRIORITY 4 [ TICKS 30 ALLOT 1 TIME 31 (of 200) ]
[ time 269 ] Run JOB 0 at PRIORITY 4 [ TICKS 29 ALLOT 1 TIME 30 (of 200) ]
[ time 270 ] Run JOB 0 at PRIORITY 4 [ TICKS 28 ALLOT 1 TIME 29 (of 200) ]
[ time 271 ] Run JOB 0 at PRIORITY 4 [ TICKS 27 ALLOT 1 TIME 28 (of 200) ]
[ time 272 ] Run JOB 0 at PRIORITY 4 [ TICKS 26 ALLOT 1 TIME 27 (of 200) ]
[ time 273 ] Run JOB 0 at PRIORITY 4 [ TICKS 25 ALLOT 1 TIME 26 (of 200) ]
[ time 274 ] Run JOB 0 at PRIORITY 4 [ TICKS 24 ALLOT 1 TIME 25 (of 200) ]
[ time 275 ] Run JOB 0 at PRIORITY 4 [ TICKS 23 ALLOT 1 TIME 24 (of 200) ]
[ time 276 ] Run JOB 0 at PRIORITY 4 [ TICKS 22 ALLOT 1 TIME 23 (of 200) ]
[ time 277 ] Run JOB 0 at PRIORITY 4 [ TICKS 21 ALLOT 1 TIME 22 (of 200) ]
[ time 278 ] Run JOB 0 at PRIORITY 4 [ TICKS 20 ALLOT 1 TIME 21 (of 200) ]
[ time 279 ] Run JOB 0 at PRIORITY 4 [ TICKS 19 ALLOT 1 TIME 20 (of 200) ]
[ time 280 ] Run JOB 0 at PRIORITY 4 [ TICKS 18 ALLOT 1 TIME 19 (of 200) ]
[ time 281 ] Run JOB 0 at PRIORITY 4 [ TICKS 17 ALLOT 1 TIME 18 (of 200) ]
[ time 282 ] Run JOB 0 at PRIORITY 4 [ TICKS 16 ALLOT 1 TIME 17 (of 200) ]
[ time 283 ] Run JOB 0 at PRIORITY 4 [ TICKS 15 ALLOT 1 TIME 16 (of 200) ]
[ time 284 ] Run JOB 0 at PRIORITY 4 [ TICKS 14 ALLOT 1 TIME 15 (of 200) ]
[ time 285 ] Run JOB 0 at PRIORITY 4 [ TICKS 13 ALLOT 1 TIME 14 (of 200) ]
[ time 286 ] Run JOB 0 at PRIORITY 4 [ TICKS 12 ALLOT 1 TIME 13 (of 200) ]
[ time 287 ] Run JOB 0 at PRIORITY 4 [ TICKS 11 ALLOT 1 TIME 12 (of 200) ]
[ time 288 ] Run JOB 0 at PRIORITY 4 [ TICKS 10 ALLOT 1 TIME 11 (of 200) ]
[ time 289 ] Run JOB 0 at PRIORITY 4 [ TICKS 9 ALLOT 1 TIME 10 (of 200) ]
[ time 290 ] Run JOB 0 at PRIORITY 4 [ TICKS 8 ALLOT 1 TIME 9 (of 200) ]
[ time 291 ] Run JOB 0 at PRIORITY 4 [ TICKS 7 ALLOT 1 TIME 8 (of 200) ]
[ time 292 ] Run JOB 0 at PRIORITY 4 [ TICKS 6 ALLOT 1 TIME 7 (of 200) ]
[ time 293 ] Run JOB 0 at PRIORITY 4 [ TICKS 5 ALLOT 1 TIME 6 (of 200) ]
[ time 294 ] Run JOB 0 at PRIORITY 4 [ TICKS 4 ALLOT 1 TIME 5 (of 200) ]
[ time 295 ] Run JOB 0 at PRIORITY 4 [ TICKS 3 ALLOT 1 TIME 4 (of 200) ]
[ time 296 ] Run JOB 0 at PRIORITY 4 [ TICKS 2 ALLOT 1 TIME 3 (of 200) ]
[ time 297 ] Run JOB 0 at PRIORITY 4 [ TICKS 1 ALLOT 1 TIME 2 (of 200) ]
[ time 298 ] IO_START by JOB 0
IO DONE
[ time 298 ] Run JOB 1 at PRIORITY 3 [ TICKS 99 ALLOT 1 TIME 99 (of 200) ]
[ time 299 ] IO_DONE by JOB 0
[ time 299 ] Run JOB 0 at PRIORITY 4 [ TICKS 99 ALLOT 1 TIME 1 (of 200) ]
[ time 300 ] Run JOB 0 at PRIORITY 4 [ TICKS 98 ALLOT 1 TIME 0 (of 200) ]
[ time 301 ] FINISHED JOB 0
[ time 301 ] Run JOB 1 at PRIORITY 3 [ TICKS 98 ALLOT 1 TIME 98 (of 200) ]
[ time 302 ] Run JOB 1 at PRIORITY 3 [ TICKS 97 ALLOT 1 TIME 97 (of 200) ]
[ time 303 ] Run JOB 1 at PRIORITY 3 [ TICKS 96 ALLOT 1 TIME 96 (of 200) ]
[ time 304 ] Run JOB 1 at PRIORITY 3 [ TICKS 95 ALLOT 1 TIME 95 (of 200) ]
[ time 305 ] Run JOB 1 at PRIORITY 3 [ TICKS 94 ALLOT 1 TIME 94 (of 200) ]
[ time 306 ] Run JOB 1 at PRIORITY 3 [ TICKS 93 ALLOT 1 TIME 93 (of 200) ]
[ time 307 ] Run JOB 1 at PRIORITY 3 [ TICKS 92 ALLOT 1 TIME 92 (of 200) ]
[ time 308 ] Run JOB 1 at PRIORITY 3 [ TICKS 91 ALLOT 1 TIME 91 (of 200) ]
[ time 309 ] Run JOB 1 at PRIORITY 3 [ TICKS 90 ALLOT 1 TIME 90 (of 200) ]
[ time 310 ] Run JOB 1 at PRIORITY 3 [ TICKS 89 ALLOT 1 TIME 89 (of 200) ]
[ time 311 ] Run JOB 1 at PRIORITY 3 [ TICKS 88 ALLOT 1 TIME 88 (of 200) ]
[ time 312 ] Run JOB 1 at PRIORITY 3 [ TICKS 87 ALLOT 1 TIME 87 (of 200) ]
[ time 313 ] Run JOB 1 at PRIORITY 3 [ TICKS 86 ALLOT 1 TIME 86 (of 200) ]
[ time 314 ] Run JOB 1 at PRIORITY 3 [ TICKS 85 ALLOT 1 TIME 85 (of 200) ]
[ time 315 ] Run JOB 1 at PRIORITY 3 [ TICKS 84 ALLOT 1 TIME 84 (of 200) ]
[ time 316 ] Run JOB 1 at PRIORITY 3 [ TICKS 83 ALLOT 1 TIME 83 (of 200) ]
[ time 317 ] Run JOB 1 at PRIORITY 3 [ TICKS 82 ALLOT 1 TIME 82 (of 200) ]
[ time 318 ] Run JOB 1 at PRIORITY 3 [ TICKS 81 ALLOT 1 TIME 81 (of 200) ]
[ time 319 ] Run JOB 1 at PRIORITY 3 [ TICKS 80 ALLOT 1 TIME 80 (of 200) ]
[ time 320 ] Run JOB 1 at PRIORITY 3 [ TICKS 79 ALLOT 1 TIME 79 (of 200) ]
[ time 321 ] Run JOB 1 at PRIORITY 3 [ TICKS 78 ALLOT 1 TIME 78 (of 200) ]
[ time 322 ] Run JOB 1 at PRIORITY 3 [ TICKS 77 ALLOT 1 TIME 77 (of 200) ]
[ time 323 ] Run JOB 1 at PRIORITY 3 [ TICKS 76 ALLOT 1 TIME 76 (of 200) ]
[ time 324 ] Run JOB 1 at PRIORITY 3 [ TICKS 75 ALLOT 1 TIME 75 (of 200) ]
[ time 325 ] Run JOB 1 at PRIORITY 3 [ TICKS 74 ALLOT 1 TIME 74 (of 200) ]
[ time 326 ] Run JOB 1 at PRIORITY 3 [ TICKS 73 ALLOT 1 TIME 73 (of 200) ]
[ time 327 ] Run JOB 1 at PRIORITY 3 [ TICKS 72 ALLOT 1 TIME 72 (of 200) ]
[ time 328 ] Run JOB 1 at PRIORITY 3 [ TICKS 71 ALLOT 1 TIME 71 (of 200) ]
[ time 329 ] Run JOB 1 at PRIORITY 3 [ TICKS 70 ALLOT 1 TIME 70 (of 200) ]
[ time 330 ] Run JOB 1 at PRIORITY 3 [ TICKS 69 ALLOT 1 TIME 69 (of 200) ]
[ time 331 ] Run JOB 1 at PRIORITY 3 [ TICKS 68 ALLOT 1 TIME 68 (of 200) ]
[ time 332 ] Run JOB 1 at PRIORITY 3 [ TICKS 67 ALLOT 1 TIME 67 (of 200) ]
[ time 333 ] Run JOB 1 at PRIORITY 3 [ TICKS 66 ALLOT 1 TIME 66 (of 200) ]
[ time 334 ] Run JOB 1 at PRIORITY 3 [ TICKS 65 ALLOT 1 TIME 65 (of 200) ]
[ time 335 ] Run JOB 1 at PRIORITY 3 [ TICKS 64 ALLOT 1 TIME 64 (of 200) ]
[ time 336 ] Run JOB 1 at PRIORITY 3 [ TICKS 63 ALLOT 1 TIME 63 (of 200) ]
[ time 337 ] Run JOB 1 at PRIORITY 3 [ TICKS 62 ALLOT 1 TIME 62 (of 200) ]
[ time 338 ] Run JOB 1 at PRIORITY 3 [ TICKS 61 ALLOT 1 TIME 61 (of 200) ]
[ time 339 ] Run JOB 1 at PRIORITY 3 [ TICKS 60 ALLOT 1 TIME 60 (of 200) ]
[ time 340 ] Run JOB 1 at PRIORITY 3 [ TICKS 59 ALLOT 1 TIME 59 (of 200) ]
[ time 341 ] Run JOB 1 at PRIORITY 3 [ TICKS 58 ALLOT 1 TIME 58 (of 200) ]
[ time 342 ] Run JOB 1 at PRIORITY 3 [ TICKS 57 ALLOT 1 TIME 57 (of 200) ]
[ time 343 ] Run JOB 1 at PRIORITY 3 [ TICKS 56 ALLOT 1 TIME 56 (of 200) ]
[ time 344 ] Run JOB 1 at PRIORITY 3 [ TICKS 55 ALLOT 1 TIME 55 (of 200) ]
[ time 345 ] Run JOB 1 at PRIORITY 3 [ TICKS 54 ALLOT 1 TIME 54 (of 200) ]
[ time 346 ] Run JOB 1 at PRIORITY 3 [ TICKS 53 ALLOT 1 TIME 53 (of 200) ]
[ time 347 ] Run JOB 1 at PRIORITY 3 [ TICKS 52 ALLOT 1 TIME 52 (of 200) ]
[ time 348 ] Run JOB 1 at PRIORITY 3 [ TICKS 51 ALLOT 1 TIME 51 (of 200) ]
[ time 349 ] Run JOB 1 at PRIORITY 3 [ TICKS 50 ALLOT 1 TIME 50 (of 200) ]
[ time 350 ] Run JOB 1 at PRIORITY 3 [ TICKS 49 ALLOT 1 TIME 49 (of 200) ]
[ time 351 ] Run JOB 1 at PRIORITY 3 [ TICKS 48 ALLOT 1 TIME 48 (of 200) ]
[ time 352 ] Run JOB 1 at PRIORITY 3 [ TICKS 47 ALLOT 1 TIME 47 (of 200) ]
[ time 353 ] Run JOB 1 at PRIORITY 3 [ TICKS 46 ALLOT 1 TIME 46 (of 200) ]
[ time 354 ] Run JOB 1 at PRIORITY 3 [ TICKS 45 ALLOT 1 TIME 45 (of 200) ]
[ time 355 ] Run JOB 1 at PRIORITY 3 [ TICKS 44 ALLOT 1 TIME 44 (of 200) ]
[ time 356 ] Run JOB 1 at PRIORITY 3 [ TICKS 43 ALLOT 1 TIME 43 (of 200) ]
[ time 357 ] Run JOB 1 at PRIORITY 3 [ TICKS 42 ALLOT 1 TIME 42 (of 200) ]
[ time 358 ] Run JOB 1 at PRIORITY 3 [ TICKS 41 ALLOT 1 TIME 41 (of 200) ]
[ time 359 ] Run JOB 1 at PRIORITY 3 [ TICKS 40 ALLOT 1 TIME 40 (of 200) ]
[ time 360 ] Run JOB 1 at PRIORITY 3 [ TICKS 39 ALLOT 1 TIME 39 (of 200) ]
[ time 361 ] Run JOB 1 at PRIORITY 3 [ TICKS 38 ALLOT 1 TIME 38 (of 200) ]
[ time 362 ] Run JOB 1 at PRIORITY 3 [ TICKS 37 ALLOT 1 TIME 37 (of 200) ]
[ time 363 ] Run JOB 1 at PRIORITY 3 [ TICKS 36 ALLOT 1 TIME 36 (of 200) ]
[ time 364 ] Run JOB 1 at PRIORITY 3 [ TICKS 35 ALLOT 1 TIME 35 (of 200) ]
[ time 365 ] Run JOB 1 at PRIORITY 3 [ TICKS 34 ALLOT 1 TIME 34 (of 200) ]
[ time 366 ] Run JOB 1 at PRIORITY 3 [ TICKS 33 ALLOT 1 TIME 33 (of 200) ]
[ time 367 ] Run JOB 1 at PRIORITY 3 [ TICKS 32 ALLOT 1 TIME 32 (of 200) ]
[ time 368 ] Run JOB 1 at PRIORITY 3 [ TICKS 31 ALLOT 1 TIME 31 (of 200) ]
[ time 369 ] Run JOB 1 at PRIORITY 3 [ TICKS 30 ALLOT 1 TIME 30 (of 200) ]
[ time 370 ] Run JOB 1 at PRIORITY 3 [ TICKS 29 ALLOT 1 TIME 29 (of 200) ]
[ time 371 ] Run JOB 1 at PRIORITY 3 [ TICKS 28 ALLOT 1 TIME 28 (of 200) ]
[ time 372 ] Run JOB 1 at PRIORITY 3 [ TICKS 27 ALLOT 1 TIME 27 (of 200) ]
[ time 373 ] Run JOB 1 at PRIORITY 3 [ TICKS 26 ALLOT 1 TIME 26 (of 200) ]
[ time 374 ] Run JOB 1 at PRIORITY 3 [ TICKS 25 ALLOT 1 TIME 25 (of 200) ]
[ time 375 ] Run JOB 1 at PRIORITY 3 [ TICKS 24 ALLOT 1 TIME 24 (of 200) ]
[ time 376 ] Run JOB 1 at PRIORITY 3 [ TICKS 23 ALLOT 1 TIME 23 (of 200) ]
[ time 377 ] Run JOB 1 at PRIORITY 3 [ TICKS 22 ALLOT 1 TIME 22 (of 200) ]
[ time 378 ] Run JOB 1 at PRIORITY 3 [ TICKS 21 ALLOT 1 TIME 21 (of 200) ]
[ time 379 ] Run JOB 1 at PRIORITY 3 [ TICKS 20 ALLOT 1 TIME 20 (of 200) ]
[ time 380 ] Run JOB 1 at PRIORITY 3 [ TICKS 19 ALLOT 1 TIME 19 (of 200) ]
[ time 381 ] Run JOB 1 at PRIORITY 3 [ TICKS 18 ALLOT 1 TIME 18 (of 200) ]
[ time 382 ] Run JOB 1 at PRIORITY 3 [ TICKS 17 ALLOT 1 TIME 17 (of 200) ]
[ time 383 ] Run JOB 1 at PRIORITY 3 [ TICKS 16 ALLOT 1 TIME 16 (of 200) ]
[ time 384 ] Run JOB 1 at PRIORITY 3 [ TICKS 15 ALLOT 1 TIME 15 (of 200) ]
[ time 385 ] Run JOB 1 at PRIORITY 3 [ TICKS 14 ALLOT 1 TIME 14 (of 200) ]
[ time 386 ] Run JOB 1 at PRIORITY 3 [ TICKS 13 ALLOT 1 TIME 13 (of 200) ]
[ time 387 ] Run JOB 1 at PRIORITY 3 [ TICKS 12 ALLOT 1 TIME 12 (of 200) ]
[ time 388 ] Run JOB 1 at PRIORITY 3 [ TICKS 11 ALLOT 1 TIME 11 (of 200) ]
[ time 389 ] Run JOB 1 at PRIORITY 3 [ TICKS 10 ALLOT 1 TIME 10 (of 200) ]
[ time 390 ] Run JOB 1 at PRIORITY 3 [ TICKS 9 ALLOT 1 TIME 9 (of 200) ]
[ time 391 ] Run JOB 1 at PRIORITY 3 [ TICKS 8 ALLOT 1 TIME 8 (of 200) ]
[ time 392 ] Run JOB 1 at PRIORITY 3 [ TICKS 7 ALLOT 1 TIME 7 (of 200) ]
[ time 393 ] Run JOB 1 at PRIORITY 3 [ TICKS 6 ALLOT 1 TIME 6 (of 200) ]
[ time 394 ] Run JOB 1 at PRIORITY 3 [ TICKS 5 ALLOT 1 TIME 5 (of 200) ]
[ time 395 ] Run JOB 1 at PRIORITY 3 [ TICKS 4 ALLOT 1 TIME 4 (of 200) ]
[ time 396 ] Run JOB 1 at PRIORITY 3 [ TICKS 3 ALLOT 1 TIME 3 (of 200) ]
[ time 397 ] Run JOB 1 at PRIORITY 3 [ TICKS 2 ALLOT 1 TIME 2 (of 200) ]
[ time 398 ] Run JOB 1 at PRIORITY 3 [ TICKS 1 ALLOT 1 TIME 1 (of 200) ]
[ time 399 ] Run JOB 1 at PRIORITY 3 [ TICKS 0 ALLOT 1 TIME 0 (of 200) ]
[ time 400 ] FINISHED JOB 1
```

**5．给定一个系统，其最高队列中的时间片长度为 10ms，你需要如何频繁地将工作推回到最高优先级级别（带有-B 标志），以保证一个长时间运行（并可能饥饿）的工作得到至少5%的 CPU？**

```sh
 ./mlfq.py --jlist 0,200,9:0,200,0 -i 1 -n 5 -q 10 -S -B 100 -c
Here is the list of inputs:
OPTIONS jobs 2
OPTIONS queues 5
OPTIONS allotments for queue  4 is   1
OPTIONS quantum length for queue  4 is  10
OPTIONS allotments for queue  3 is   1
OPTIONS quantum length for queue  3 is  10
OPTIONS allotments for queue  2 is   1
OPTIONS quantum length for queue  2 is  10
OPTIONS allotments for queue  1 is   1
OPTIONS quantum length for queue  1 is  10
OPTIONS allotments for queue  0 is   1
OPTIONS quantum length for queue  0 is  10
OPTIONS boost 100
OPTIONS ioTime 1
OPTIONS stayAfterIO True
OPTIONS iobump False


For each job, three defining characteristics are given:
  startTime : at what time does the job enter the system
  runTime   : the total CPU time needed by the job to finish
  ioFreq    : every ioFreq time units, the job issues an I/O
              (the I/O takes ioTime units to complete)

Job List:
  Job  0: startTime   0 - runTime 200 - ioFreq   9
  Job  1: startTime   0 - runTime 200 - ioFreq   0


Execution Trace:

[ time 0 ] JOB BEGINS by JOB 0
[ time 0 ] JOB BEGINS by JOB 1
[ time 0 ] Run JOB 0 at PRIORITY 4 [ TICKS 9 ALLOT 1 TIME 199 (of 200) ]
[ time 1 ] Run JOB 0 at PRIORITY 4 [ TICKS 8 ALLOT 1 TIME 198 (of 200) ]
[ time 2 ] Run JOB 0 at PRIORITY 4 [ TICKS 7 ALLOT 1 TIME 197 (of 200) ]
[ time 3 ] Run JOB 0 at PRIORITY 4 [ TICKS 6 ALLOT 1 TIME 196 (of 200) ]
[ time 4 ] Run JOB 0 at PRIORITY 4 [ TICKS 5 ALLOT 1 TIME 195 (of 200) ]
[ time 5 ] Run JOB 0 at PRIORITY 4 [ TICKS 4 ALLOT 1 TIME 194 (of 200) ]
[ time 6 ] Run JOB 0 at PRIORITY 4 [ TICKS 3 ALLOT 1 TIME 193 (of 200) ]
[ time 7 ] Run JOB 0 at PRIORITY 4 [ TICKS 2 ALLOT 1 TIME 192 (of 200) ]
[ time 8 ] Run JOB 0 at PRIORITY 4 [ TICKS 1 ALLOT 1 TIME 191 (of 200) ]
[ time 9 ] IO_START by JOB 0
IO DONE
[ time 9 ] Run JOB 1 at PRIORITY 4 [ TICKS 9 ALLOT 1 TIME 199 (of 200) ]
[ time 10 ] IO_DONE by JOB 0
[ time 10 ] Run JOB 1 at PRIORITY 4 [ TICKS 8 ALLOT 1 TIME 198 (of 200) ]
[ time 11 ] Run JOB 1 at PRIORITY 4 [ TICKS 7 ALLOT 1 TIME 197 (of 200) ]
[ time 12 ] Run JOB 1 at PRIORITY 4 [ TICKS 6 ALLOT 1 TIME 196 (of 200) ]
[ time 13 ] Run JOB 1 at PRIORITY 4 [ TICKS 5 ALLOT 1 TIME 195 (of 200) ]
[ time 14 ] Run JOB 1 at PRIORITY 4 [ TICKS 4 ALLOT 1 TIME 194 (of 200) ]
[ time 15 ] Run JOB 1 at PRIORITY 4 [ TICKS 3 ALLOT 1 TIME 193 (of 200) ]
[ time 16 ] Run JOB 1 at PRIORITY 4 [ TICKS 2 ALLOT 1 TIME 192 (of 200) ]
[ time 17 ] Run JOB 1 at PRIORITY 4 [ TICKS 1 ALLOT 1 TIME 191 (of 200) ]
[ time 18 ] Run JOB 1 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 190 (of 200) ]
[ time 19 ] Run JOB 0 at PRIORITY 4 [ TICKS 9 ALLOT 1 TIME 190 (of 200) ]
[ time 20 ] Run JOB 0 at PRIORITY 4 [ TICKS 8 ALLOT 1 TIME 189 (of 200) ]
[ time 21 ] Run JOB 0 at PRIORITY 4 [ TICKS 7 ALLOT 1 TIME 188 (of 200) ]
[ time 22 ] Run JOB 0 at PRIORITY 4 [ TICKS 6 ALLOT 1 TIME 187 (of 200) ]
[ time 23 ] Run JOB 0 at PRIORITY 4 [ TICKS 5 ALLOT 1 TIME 186 (of 200) ]
[ time 24 ] Run JOB 0 at PRIORITY 4 [ TICKS 4 ALLOT 1 TIME 185 (of 200) ]
[ time 25 ] Run JOB 0 at PRIORITY 4 [ TICKS 3 ALLOT 1 TIME 184 (of 200) ]
[ time 26 ] Run JOB 0 at PRIORITY 4 [ TICKS 2 ALLOT 1 TIME 183 (of 200) ]
[ time 27 ] Run JOB 0 at PRIORITY 4 [ TICKS 1 ALLOT 1 TIME 182 (of 200) ]
[ time 28 ] IO_START by JOB 0
IO DONE
[ time 28 ] Run JOB 1 at PRIORITY 3 [ TICKS 9 ALLOT 1 TIME 189 (of 200) ]
[ time 29 ] IO_DONE by JOB 0
[ time 29 ] Run JOB 0 at PRIORITY 4 [ TICKS 9 ALLOT 1 TIME 181 (of 200) ]
[ time 30 ] Run JOB 0 at PRIORITY 4 [ TICKS 8 ALLOT 1 TIME 180 (of 200) ]
[ time 31 ] Run JOB 0 at PRIORITY 4 [ TICKS 7 ALLOT 1 TIME 179 (of 200) ]
[ time 32 ] Run JOB 0 at PRIORITY 4 [ TICKS 6 ALLOT 1 TIME 178 (of 200) ]
[ time 33 ] Run JOB 0 at PRIORITY 4 [ TICKS 5 ALLOT 1 TIME 177 (of 200) ]
[ time 34 ] Run JOB 0 at PRIORITY 4 [ TICKS 4 ALLOT 1 TIME 176 (of 200) ]
[ time 35 ] Run JOB 0 at PRIORITY 4 [ TICKS 3 ALLOT 1 TIME 175 (of 200) ]
[ time 36 ] Run JOB 0 at PRIORITY 4 [ TICKS 2 ALLOT 1 TIME 174 (of 200) ]
[ time 37 ] Run JOB 0 at PRIORITY 4 [ TICKS 1 ALLOT 1 TIME 173 (of 200) ]
[ time 38 ] IO_START by JOB 0
IO DONE
[ time 38 ] Run JOB 1 at PRIORITY 3 [ TICKS 8 ALLOT 1 TIME 188 (of 200) ]
[ time 39 ] IO_DONE by JOB 0
[ time 39 ] Run JOB 0 at PRIORITY 4 [ TICKS 9 ALLOT 1 TIME 172 (of 200) ]
[ time 40 ] Run JOB 0 at PRIORITY 4 [ TICKS 8 ALLOT 1 TIME 171 (of 200) ]
[ time 41 ] Run JOB 0 at PRIORITY 4 [ TICKS 7 ALLOT 1 TIME 170 (of 200) ]
[ time 42 ] Run JOB 0 at PRIORITY 4 [ TICKS 6 ALLOT 1 TIME 169 (of 200) ]
[ time 43 ] Run JOB 0 at PRIORITY 4 [ TICKS 5 ALLOT 1 TIME 168 (of 200) ]
[ time 44 ] Run JOB 0 at PRIORITY 4 [ TICKS 4 ALLOT 1 TIME 167 (of 200) ]
[ time 45 ] Run JOB 0 at PRIORITY 4 [ TICKS 3 ALLOT 1 TIME 166 (of 200) ]
[ time 46 ] Run JOB 0 at PRIORITY 4 [ TICKS 2 ALLOT 1 TIME 165 (of 200) ]
[ time 47 ] Run JOB 0 at PRIORITY 4 [ TICKS 1 ALLOT 1 TIME 164 (of 200) ]
[ time 48 ] IO_START by JOB 0
IO DONE
[ time 48 ] Run JOB 1 at PRIORITY 3 [ TICKS 7 ALLOT 1 TIME 187 (of 200) ]
[ time 49 ] IO_DONE by JOB 0
[ time 49 ] Run JOB 0 at PRIORITY 4 [ TICKS 9 ALLOT 1 TIME 163 (of 200) ]
[ time 50 ] Run JOB 0 at PRIORITY 4 [ TICKS 8 ALLOT 1 TIME 162 (of 200) ]
[ time 51 ] Run JOB 0 at PRIORITY 4 [ TICKS 7 ALLOT 1 TIME 161 (of 200) ]
[ time 52 ] Run JOB 0 at PRIORITY 4 [ TICKS 6 ALLOT 1 TIME 160 (of 200) ]
[ time 53 ] Run JOB 0 at PRIORITY 4 [ TICKS 5 ALLOT 1 TIME 159 (of 200) ]
[ time 54 ] Run JOB 0 at PRIORITY 4 [ TICKS 4 ALLOT 1 TIME 158 (of 200) ]
[ time 55 ] Run JOB 0 at PRIORITY 4 [ TICKS 3 ALLOT 1 TIME 157 (of 200) ]
[ time 56 ] Run JOB 0 at PRIORITY 4 [ TICKS 2 ALLOT 1 TIME 156 (of 200) ]
[ time 57 ] Run JOB 0 at PRIORITY 4 [ TICKS 1 ALLOT 1 TIME 155 (of 200) ]
[ time 58 ] IO_START by JOB 0
IO DONE
[ time 58 ] Run JOB 1 at PRIORITY 3 [ TICKS 6 ALLOT 1 TIME 186 (of 200) ]
[ time 59 ] IO_DONE by JOB 0
[ time 59 ] Run JOB 0 at PRIORITY 4 [ TICKS 9 ALLOT 1 TIME 154 (of 200) ]
[ time 60 ] Run JOB 0 at PRIORITY 4 [ TICKS 8 ALLOT 1 TIME 153 (of 200) ]
[ time 61 ] Run JOB 0 at PRIORITY 4 [ TICKS 7 ALLOT 1 TIME 152 (of 200) ]
[ time 62 ] Run JOB 0 at PRIORITY 4 [ TICKS 6 ALLOT 1 TIME 151 (of 200) ]
[ time 63 ] Run JOB 0 at PRIORITY 4 [ TICKS 5 ALLOT 1 TIME 150 (of 200) ]
[ time 64 ] Run JOB 0 at PRIORITY 4 [ TICKS 4 ALLOT 1 TIME 149 (of 200) ]
[ time 65 ] Run JOB 0 at PRIORITY 4 [ TICKS 3 ALLOT 1 TIME 148 (of 200) ]
[ time 66 ] Run JOB 0 at PRIORITY 4 [ TICKS 2 ALLOT 1 TIME 147 (of 200) ]
[ time 67 ] Run JOB 0 at PRIORITY 4 [ TICKS 1 ALLOT 1 TIME 146 (of 200) ]
[ time 68 ] IO_START by JOB 0
IO DONE
[ time 68 ] Run JOB 1 at PRIORITY 3 [ TICKS 5 ALLOT 1 TIME 185 (of 200) ]
[ time 69 ] IO_DONE by JOB 0
[ time 69 ] Run JOB 0 at PRIORITY 4 [ TICKS 9 ALLOT 1 TIME 145 (of 200) ]
[ time 70 ] Run JOB 0 at PRIORITY 4 [ TICKS 8 ALLOT 1 TIME 144 (of 200) ]
[ time 71 ] Run JOB 0 at PRIORITY 4 [ TICKS 7 ALLOT 1 TIME 143 (of 200) ]
[ time 72 ] Run JOB 0 at PRIORITY 4 [ TICKS 6 ALLOT 1 TIME 142 (of 200) ]
[ time 73 ] Run JOB 0 at PRIORITY 4 [ TICKS 5 ALLOT 1 TIME 141 (of 200) ]
[ time 74 ] Run JOB 0 at PRIORITY 4 [ TICKS 4 ALLOT 1 TIME 140 (of 200) ]
[ time 75 ] Run JOB 0 at PRIORITY 4 [ TICKS 3 ALLOT 1 TIME 139 (of 200) ]
[ time 76 ] Run JOB 0 at PRIORITY 4 [ TICKS 2 ALLOT 1 TIME 138 (of 200) ]
[ time 77 ] Run JOB 0 at PRIORITY 4 [ TICKS 1 ALLOT 1 TIME 137 (of 200) ]
[ time 78 ] IO_START by JOB 0
IO DONE
[ time 78 ] Run JOB 1 at PRIORITY 3 [ TICKS 4 ALLOT 1 TIME 184 (of 200) ]
[ time 79 ] IO_DONE by JOB 0
[ time 79 ] Run JOB 0 at PRIORITY 4 [ TICKS 9 ALLOT 1 TIME 136 (of 200) ]
[ time 80 ] Run JOB 0 at PRIORITY 4 [ TICKS 8 ALLOT 1 TIME 135 (of 200) ]
[ time 81 ] Run JOB 0 at PRIORITY 4 [ TICKS 7 ALLOT 1 TIME 134 (of 200) ]
[ time 82 ] Run JOB 0 at PRIORITY 4 [ TICKS 6 ALLOT 1 TIME 133 (of 200) ]
[ time 83 ] Run JOB 0 at PRIORITY 4 [ TICKS 5 ALLOT 1 TIME 132 (of 200) ]
[ time 84 ] Run JOB 0 at PRIORITY 4 [ TICKS 4 ALLOT 1 TIME 131 (of 200) ]
[ time 85 ] Run JOB 0 at PRIORITY 4 [ TICKS 3 ALLOT 1 TIME 130 (of 200) ]
[ time 86 ] Run JOB 0 at PRIORITY 4 [ TICKS 2 ALLOT 1 TIME 129 (of 200) ]
[ time 87 ] Run JOB 0 at PRIORITY 4 [ TICKS 1 ALLOT 1 TIME 128 (of 200) ]
[ time 88 ] IO_START by JOB 0
IO DONE
[ time 88 ] Run JOB 1 at PRIORITY 3 [ TICKS 3 ALLOT 1 TIME 183 (of 200) ]
[ time 89 ] IO_DONE by JOB 0
[ time 89 ] Run JOB 0 at PRIORITY 4 [ TICKS 9 ALLOT 1 TIME 127 (of 200) ]
[ time 90 ] Run JOB 0 at PRIORITY 4 [ TICKS 8 ALLOT 1 TIME 126 (of 200) ]
[ time 91 ] Run JOB 0 at PRIORITY 4 [ TICKS 7 ALLOT 1 TIME 125 (of 200) ]
[ time 92 ] Run JOB 0 at PRIORITY 4 [ TICKS 6 ALLOT 1 TIME 124 (of 200) ]
[ time 93 ] Run JOB 0 at PRIORITY 4 [ TICKS 5 ALLOT 1 TIME 123 (of 200) ]
[ time 94 ] Run JOB 0 at PRIORITY 4 [ TICKS 4 ALLOT 1 TIME 122 (of 200) ]
[ time 95 ] Run JOB 0 at PRIORITY 4 [ TICKS 3 ALLOT 1 TIME 121 (of 200) ]
[ time 96 ] Run JOB 0 at PRIORITY 4 [ TICKS 2 ALLOT 1 TIME 120 (of 200) ]
[ time 97 ] Run JOB 0 at PRIORITY 4 [ TICKS 1 ALLOT 1 TIME 119 (of 200) ]
[ time 98 ] IO_START by JOB 0
IO DONE
[ time 98 ] Run JOB 1 at PRIORITY 3 [ TICKS 2 ALLOT 1 TIME 182 (of 200) ]
[ time 99 ] IO_DONE by JOB 0
[ time 99 ] Run JOB 0 at PRIORITY 4 [ TICKS 9 ALLOT 1 TIME 118 (of 200) ]
[ time 100 ] BOOST ( every 100 )
[ time 100 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 117 (of 200) ]
[ time 101 ] Run JOB 1 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 181 (of 200) ]
[ time 102 ] Run JOB 0 at PRIORITY 3 [ TICKS 9 ALLOT 1 TIME 116 (of 200) ]
[ time 103 ] Run JOB 0 at PRIORITY 3 [ TICKS 8 ALLOT 1 TIME 115 (of 200) ]
[ time 104 ] Run JOB 0 at PRIORITY 3 [ TICKS 7 ALLOT 1 TIME 114 (of 200) ]
[ time 105 ] Run JOB 0 at PRIORITY 3 [ TICKS 6 ALLOT 1 TIME 113 (of 200) ]
[ time 106 ] Run JOB 0 at PRIORITY 3 [ TICKS 5 ALLOT 1 TIME 112 (of 200) ]
[ time 107 ] Run JOB 0 at PRIORITY 3 [ TICKS 4 ALLOT 1 TIME 111 (of 200) ]
[ time 108 ] Run JOB 0 at PRIORITY 3 [ TICKS 3 ALLOT 1 TIME 110 (of 200) ]
[ time 109 ] IO_START by JOB 0
IO DONE
[ time 109 ] Run JOB 1 at PRIORITY 3 [ TICKS 9 ALLOT 1 TIME 180 (of 200) ]
[ time 110 ] IO_DONE by JOB 0
[ time 110 ] Run JOB 1 at PRIORITY 3 [ TICKS 8 ALLOT 1 TIME 179 (of 200) ]
[ time 111 ] Run JOB 1 at PRIORITY 3 [ TICKS 7 ALLOT 1 TIME 178 (of 200) ]
[ time 112 ] Run JOB 1 at PRIORITY 3 [ TICKS 6 ALLOT 1 TIME 177 (of 200) ]
[ time 113 ] Run JOB 1 at PRIORITY 3 [ TICKS 5 ALLOT 1 TIME 176 (of 200) ]
[ time 114 ] Run JOB 1 at PRIORITY 3 [ TICKS 4 ALLOT 1 TIME 175 (of 200) ]
[ time 115 ] Run JOB 1 at PRIORITY 3 [ TICKS 3 ALLOT 1 TIME 174 (of 200) ]
[ time 116 ] Run JOB 1 at PRIORITY 3 [ TICKS 2 ALLOT 1 TIME 173 (of 200) ]
[ time 117 ] Run JOB 1 at PRIORITY 3 [ TICKS 1 ALLOT 1 TIME 172 (of 200) ]
[ time 118 ] Run JOB 1 at PRIORITY 3 [ TICKS 0 ALLOT 1 TIME 171 (of 200) ]
[ time 119 ] Run JOB 0 at PRIORITY 3 [ TICKS 9 ALLOT 1 TIME 109 (of 200) ]
[ time 120 ] Run JOB 0 at PRIORITY 3 [ TICKS 8 ALLOT 1 TIME 108 (of 200) ]
[ time 121 ] Run JOB 0 at PRIORITY 3 [ TICKS 7 ALLOT 1 TIME 107 (of 200) ]
[ time 122 ] Run JOB 0 at PRIORITY 3 [ TICKS 6 ALLOT 1 TIME 106 (of 200) ]
[ time 123 ] Run JOB 0 at PRIORITY 3 [ TICKS 5 ALLOT 1 TIME 105 (of 200) ]
[ time 124 ] Run JOB 0 at PRIORITY 3 [ TICKS 4 ALLOT 1 TIME 104 (of 200) ]
[ time 125 ] Run JOB 0 at PRIORITY 3 [ TICKS 3 ALLOT 1 TIME 103 (of 200) ]
[ time 126 ] Run JOB 0 at PRIORITY 3 [ TICKS 2 ALLOT 1 TIME 102 (of 200) ]
[ time 127 ] Run JOB 0 at PRIORITY 3 [ TICKS 1 ALLOT 1 TIME 101 (of 200) ]
[ time 128 ] IO_START by JOB 0
IO DONE
[ time 128 ] Run JOB 1 at PRIORITY 2 [ TICKS 9 ALLOT 1 TIME 170 (of 200) ]
[ time 129 ] IO_DONE by JOB 0
[ time 129 ] Run JOB 0 at PRIORITY 3 [ TICKS 9 ALLOT 1 TIME 100 (of 200) ]
[ time 130 ] Run JOB 0 at PRIORITY 3 [ TICKS 8 ALLOT 1 TIME 99 (of 200) ]
[ time 131 ] Run JOB 0 at PRIORITY 3 [ TICKS 7 ALLOT 1 TIME 98 (of 200) ]
[ time 132 ] Run JOB 0 at PRIORITY 3 [ TICKS 6 ALLOT 1 TIME 97 (of 200) ]
[ time 133 ] Run JOB 0 at PRIORITY 3 [ TICKS 5 ALLOT 1 TIME 96 (of 200) ]
[ time 134 ] Run JOB 0 at PRIORITY 3 [ TICKS 4 ALLOT 1 TIME 95 (of 200) ]
[ time 135 ] Run JOB 0 at PRIORITY 3 [ TICKS 3 ALLOT 1 TIME 94 (of 200) ]
[ time 136 ] Run JOB 0 at PRIORITY 3 [ TICKS 2 ALLOT 1 TIME 93 (of 200) ]
[ time 137 ] Run JOB 0 at PRIORITY 3 [ TICKS 1 ALLOT 1 TIME 92 (of 200) ]
[ time 138 ] IO_START by JOB 0
IO DONE
[ time 138 ] Run JOB 1 at PRIORITY 2 [ TICKS 8 ALLOT 1 TIME 169 (of 200) ]
[ time 139 ] IO_DONE by JOB 0
[ time 139 ] Run JOB 0 at PRIORITY 3 [ TICKS 9 ALLOT 1 TIME 91 (of 200) ]
[ time 140 ] Run JOB 0 at PRIORITY 3 [ TICKS 8 ALLOT 1 TIME 90 (of 200) ]
[ time 141 ] Run JOB 0 at PRIORITY 3 [ TICKS 7 ALLOT 1 TIME 89 (of 200) ]
[ time 142 ] Run JOB 0 at PRIORITY 3 [ TICKS 6 ALLOT 1 TIME 88 (of 200) ]
[ time 143 ] Run JOB 0 at PRIORITY 3 [ TICKS 5 ALLOT 1 TIME 87 (of 200) ]
[ time 144 ] Run JOB 0 at PRIORITY 3 [ TICKS 4 ALLOT 1 TIME 86 (of 200) ]
[ time 145 ] Run JOB 0 at PRIORITY 3 [ TICKS 3 ALLOT 1 TIME 85 (of 200) ]
[ time 146 ] Run JOB 0 at PRIORITY 3 [ TICKS 2 ALLOT 1 TIME 84 (of 200) ]
[ time 147 ] Run JOB 0 at PRIORITY 3 [ TICKS 1 ALLOT 1 TIME 83 (of 200) ]
[ time 148 ] IO_START by JOB 0
IO DONE
[ time 148 ] Run JOB 1 at PRIORITY 2 [ TICKS 7 ALLOT 1 TIME 168 (of 200) ]
[ time 149 ] IO_DONE by JOB 0
[ time 149 ] Run JOB 0 at PRIORITY 3 [ TICKS 9 ALLOT 1 TIME 82 (of 200) ]
[ time 150 ] Run JOB 0 at PRIORITY 3 [ TICKS 8 ALLOT 1 TIME 81 (of 200) ]
[ time 151 ] Run JOB 0 at PRIORITY 3 [ TICKS 7 ALLOT 1 TIME 80 (of 200) ]
[ time 152 ] Run JOB 0 at PRIORITY 3 [ TICKS 6 ALLOT 1 TIME 79 (of 200) ]
[ time 153 ] Run JOB 0 at PRIORITY 3 [ TICKS 5 ALLOT 1 TIME 78 (of 200) ]
[ time 154 ] Run JOB 0 at PRIORITY 3 [ TICKS 4 ALLOT 1 TIME 77 (of 200) ]
[ time 155 ] Run JOB 0 at PRIORITY 3 [ TICKS 3 ALLOT 1 TIME 76 (of 200) ]
[ time 156 ] Run JOB 0 at PRIORITY 3 [ TICKS 2 ALLOT 1 TIME 75 (of 200) ]
[ time 157 ] Run JOB 0 at PRIORITY 3 [ TICKS 1 ALLOT 1 TIME 74 (of 200) ]
[ time 158 ] IO_START by JOB 0
IO DONE
[ time 158 ] Run JOB 1 at PRIORITY 2 [ TICKS 6 ALLOT 1 TIME 167 (of 200) ]
[ time 159 ] IO_DONE by JOB 0
[ time 159 ] Run JOB 0 at PRIORITY 3 [ TICKS 9 ALLOT 1 TIME 73 (of 200) ]
[ time 160 ] Run JOB 0 at PRIORITY 3 [ TICKS 8 ALLOT 1 TIME 72 (of 200) ]
[ time 161 ] Run JOB 0 at PRIORITY 3 [ TICKS 7 ALLOT 1 TIME 71 (of 200) ]
[ time 162 ] Run JOB 0 at PRIORITY 3 [ TICKS 6 ALLOT 1 TIME 70 (of 200) ]
[ time 163 ] Run JOB 0 at PRIORITY 3 [ TICKS 5 ALLOT 1 TIME 69 (of 200) ]
[ time 164 ] Run JOB 0 at PRIORITY 3 [ TICKS 4 ALLOT 1 TIME 68 (of 200) ]
[ time 165 ] Run JOB 0 at PRIORITY 3 [ TICKS 3 ALLOT 1 TIME 67 (of 200) ]
[ time 166 ] Run JOB 0 at PRIORITY 3 [ TICKS 2 ALLOT 1 TIME 66 (of 200) ]
[ time 167 ] Run JOB 0 at PRIORITY 3 [ TICKS 1 ALLOT 1 TIME 65 (of 200) ]
[ time 168 ] IO_START by JOB 0
IO DONE
[ time 168 ] Run JOB 1 at PRIORITY 2 [ TICKS 5 ALLOT 1 TIME 166 (of 200) ]
[ time 169 ] IO_DONE by JOB 0
[ time 169 ] Run JOB 0 at PRIORITY 3 [ TICKS 9 ALLOT 1 TIME 64 (of 200) ]
[ time 170 ] Run JOB 0 at PRIORITY 3 [ TICKS 8 ALLOT 1 TIME 63 (of 200) ]
[ time 171 ] Run JOB 0 at PRIORITY 3 [ TICKS 7 ALLOT 1 TIME 62 (of 200) ]
[ time 172 ] Run JOB 0 at PRIORITY 3 [ TICKS 6 ALLOT 1 TIME 61 (of 200) ]
[ time 173 ] Run JOB 0 at PRIORITY 3 [ TICKS 5 ALLOT 1 TIME 60 (of 200) ]
[ time 174 ] Run JOB 0 at PRIORITY 3 [ TICKS 4 ALLOT 1 TIME 59 (of 200) ]
[ time 175 ] Run JOB 0 at PRIORITY 3 [ TICKS 3 ALLOT 1 TIME 58 (of 200) ]
[ time 176 ] Run JOB 0 at PRIORITY 3 [ TICKS 2 ALLOT 1 TIME 57 (of 200) ]
[ time 177 ] Run JOB 0 at PRIORITY 3 [ TICKS 1 ALLOT 1 TIME 56 (of 200) ]
[ time 178 ] IO_START by JOB 0
IO DONE
[ time 178 ] Run JOB 1 at PRIORITY 2 [ TICKS 4 ALLOT 1 TIME 165 (of 200) ]
[ time 179 ] IO_DONE by JOB 0
[ time 179 ] Run JOB 0 at PRIORITY 3 [ TICKS 9 ALLOT 1 TIME 55 (of 200) ]
[ time 180 ] Run JOB 0 at PRIORITY 3 [ TICKS 8 ALLOT 1 TIME 54 (of 200) ]
[ time 181 ] Run JOB 0 at PRIORITY 3 [ TICKS 7 ALLOT 1 TIME 53 (of 200) ]
[ time 182 ] Run JOB 0 at PRIORITY 3 [ TICKS 6 ALLOT 1 TIME 52 (of 200) ]
[ time 183 ] Run JOB 0 at PRIORITY 3 [ TICKS 5 ALLOT 1 TIME 51 (of 200) ]
[ time 184 ] Run JOB 0 at PRIORITY 3 [ TICKS 4 ALLOT 1 TIME 50 (of 200) ]
[ time 185 ] Run JOB 0 at PRIORITY 3 [ TICKS 3 ALLOT 1 TIME 49 (of 200) ]
[ time 186 ] Run JOB 0 at PRIORITY 3 [ TICKS 2 ALLOT 1 TIME 48 (of 200) ]
[ time 187 ] Run JOB 0 at PRIORITY 3 [ TICKS 1 ALLOT 1 TIME 47 (of 200) ]
[ time 188 ] IO_START by JOB 0
IO DONE
[ time 188 ] Run JOB 1 at PRIORITY 2 [ TICKS 3 ALLOT 1 TIME 164 (of 200) ]
[ time 189 ] IO_DONE by JOB 0
[ time 189 ] Run JOB 0 at PRIORITY 3 [ TICKS 9 ALLOT 1 TIME 46 (of 200) ]
[ time 190 ] Run JOB 0 at PRIORITY 3 [ TICKS 8 ALLOT 1 TIME 45 (of 200) ]
[ time 191 ] Run JOB 0 at PRIORITY 3 [ TICKS 7 ALLOT 1 TIME 44 (of 200) ]
[ time 192 ] Run JOB 0 at PRIORITY 3 [ TICKS 6 ALLOT 1 TIME 43 (of 200) ]
[ time 193 ] Run JOB 0 at PRIORITY 3 [ TICKS 5 ALLOT 1 TIME 42 (of 200) ]
[ time 194 ] Run JOB 0 at PRIORITY 3 [ TICKS 4 ALLOT 1 TIME 41 (of 200) ]
[ time 195 ] Run JOB 0 at PRIORITY 3 [ TICKS 3 ALLOT 1 TIME 40 (of 200) ]
[ time 196 ] Run JOB 0 at PRIORITY 3 [ TICKS 2 ALLOT 1 TIME 39 (of 200) ]
[ time 197 ] Run JOB 0 at PRIORITY 3 [ TICKS 1 ALLOT 1 TIME 38 (of 200) ]
[ time 198 ] IO_START by JOB 0
IO DONE
[ time 198 ] Run JOB 1 at PRIORITY 2 [ TICKS 2 ALLOT 1 TIME 163 (of 200) ]
[ time 199 ] IO_DONE by JOB 0
[ time 199 ] Run JOB 0 at PRIORITY 3 [ TICKS 9 ALLOT 1 TIME 37 (of 200) ]
[ time 200 ] BOOST ( every 100 )
[ time 200 ] Run JOB 1 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 162 (of 200) ]
[ time 201 ] Run JOB 0 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 36 (of 200) ]
[ time 202 ] Run JOB 1 at PRIORITY 3 [ TICKS 9 ALLOT 1 TIME 161 (of 200) ]
[ time 203 ] Run JOB 1 at PRIORITY 3 [ TICKS 8 ALLOT 1 TIME 160 (of 200) ]
[ time 204 ] Run JOB 1 at PRIORITY 3 [ TICKS 7 ALLOT 1 TIME 159 (of 200) ]
[ time 205 ] Run JOB 1 at PRIORITY 3 [ TICKS 6 ALLOT 1 TIME 158 (of 200) ]
[ time 206 ] Run JOB 1 at PRIORITY 3 [ TICKS 5 ALLOT 1 TIME 157 (of 200) ]
[ time 207 ] Run JOB 1 at PRIORITY 3 [ TICKS 4 ALLOT 1 TIME 156 (of 200) ]
[ time 208 ] Run JOB 1 at PRIORITY 3 [ TICKS 3 ALLOT 1 TIME 155 (of 200) ]
[ time 209 ] Run JOB 1 at PRIORITY 3 [ TICKS 2 ALLOT 1 TIME 154 (of 200) ]
[ time 210 ] Run JOB 1 at PRIORITY 3 [ TICKS 1 ALLOT 1 TIME 153 (of 200) ]
[ time 211 ] Run JOB 1 at PRIORITY 3 [ TICKS 0 ALLOT 1 TIME 152 (of 200) ]
[ time 212 ] Run JOB 0 at PRIORITY 3 [ TICKS 9 ALLOT 1 TIME 35 (of 200) ]
[ time 213 ] Run JOB 0 at PRIORITY 3 [ TICKS 8 ALLOT 1 TIME 34 (of 200) ]
[ time 214 ] Run JOB 0 at PRIORITY 3 [ TICKS 7 ALLOT 1 TIME 33 (of 200) ]
[ time 215 ] Run JOB 0 at PRIORITY 3 [ TICKS 6 ALLOT 1 TIME 32 (of 200) ]
[ time 216 ] Run JOB 0 at PRIORITY 3 [ TICKS 5 ALLOT 1 TIME 31 (of 200) ]
[ time 217 ] Run JOB 0 at PRIORITY 3 [ TICKS 4 ALLOT 1 TIME 30 (of 200) ]
[ time 218 ] Run JOB 0 at PRIORITY 3 [ TICKS 3 ALLOT 1 TIME 29 (of 200) ]
[ time 219 ] IO_START by JOB 0
IO DONE
[ time 219 ] Run JOB 1 at PRIORITY 2 [ TICKS 9 ALLOT 1 TIME 151 (of 200) ]
[ time 220 ] IO_DONE by JOB 0
[ time 220 ] Run JOB 0 at PRIORITY 3 [ TICKS 9 ALLOT 1 TIME 28 (of 200) ]
[ time 221 ] Run JOB 0 at PRIORITY 3 [ TICKS 8 ALLOT 1 TIME 27 (of 200) ]
[ time 222 ] Run JOB 0 at PRIORITY 3 [ TICKS 7 ALLOT 1 TIME 26 (of 200) ]
[ time 223 ] Run JOB 0 at PRIORITY 3 [ TICKS 6 ALLOT 1 TIME 25 (of 200) ]
[ time 224 ] Run JOB 0 at PRIORITY 3 [ TICKS 5 ALLOT 1 TIME 24 (of 200) ]
[ time 225 ] Run JOB 0 at PRIORITY 3 [ TICKS 4 ALLOT 1 TIME 23 (of 200) ]
[ time 226 ] Run JOB 0 at PRIORITY 3 [ TICKS 3 ALLOT 1 TIME 22 (of 200) ]
[ time 227 ] Run JOB 0 at PRIORITY 3 [ TICKS 2 ALLOT 1 TIME 21 (of 200) ]
[ time 228 ] Run JOB 0 at PRIORITY 3 [ TICKS 1 ALLOT 1 TIME 20 (of 200) ]
[ time 229 ] IO_START by JOB 0
IO DONE
[ time 229 ] Run JOB 1 at PRIORITY 2 [ TICKS 8 ALLOT 1 TIME 150 (of 200) ]
[ time 230 ] IO_DONE by JOB 0
[ time 230 ] Run JOB 0 at PRIORITY 3 [ TICKS 9 ALLOT 1 TIME 19 (of 200) ]
[ time 231 ] Run JOB 0 at PRIORITY 3 [ TICKS 8 ALLOT 1 TIME 18 (of 200) ]
[ time 232 ] Run JOB 0 at PRIORITY 3 [ TICKS 7 ALLOT 1 TIME 17 (of 200) ]
[ time 233 ] Run JOB 0 at PRIORITY 3 [ TICKS 6 ALLOT 1 TIME 16 (of 200) ]
[ time 234 ] Run JOB 0 at PRIORITY 3 [ TICKS 5 ALLOT 1 TIME 15 (of 200) ]
[ time 235 ] Run JOB 0 at PRIORITY 3 [ TICKS 4 ALLOT 1 TIME 14 (of 200) ]
[ time 236 ] Run JOB 0 at PRIORITY 3 [ TICKS 3 ALLOT 1 TIME 13 (of 200) ]
[ time 237 ] Run JOB 0 at PRIORITY 3 [ TICKS 2 ALLOT 1 TIME 12 (of 200) ]
[ time 238 ] Run JOB 0 at PRIORITY 3 [ TICKS 1 ALLOT 1 TIME 11 (of 200) ]
[ time 239 ] IO_START by JOB 0
IO DONE
[ time 239 ] Run JOB 1 at PRIORITY 2 [ TICKS 7 ALLOT 1 TIME 149 (of 200) ]
[ time 240 ] IO_DONE by JOB 0
[ time 240 ] Run JOB 0 at PRIORITY 3 [ TICKS 9 ALLOT 1 TIME 10 (of 200) ]
[ time 241 ] Run JOB 0 at PRIORITY 3 [ TICKS 8 ALLOT 1 TIME 9 (of 200) ]
[ time 242 ] Run JOB 0 at PRIORITY 3 [ TICKS 7 ALLOT 1 TIME 8 (of 200) ]
[ time 243 ] Run JOB 0 at PRIORITY 3 [ TICKS 6 ALLOT 1 TIME 7 (of 200) ]
[ time 244 ] Run JOB 0 at PRIORITY 3 [ TICKS 5 ALLOT 1 TIME 6 (of 200) ]
[ time 245 ] Run JOB 0 at PRIORITY 3 [ TICKS 4 ALLOT 1 TIME 5 (of 200) ]
[ time 246 ] Run JOB 0 at PRIORITY 3 [ TICKS 3 ALLOT 1 TIME 4 (of 200) ]
[ time 247 ] Run JOB 0 at PRIORITY 3 [ TICKS 2 ALLOT 1 TIME 3 (of 200) ]
[ time 248 ] Run JOB 0 at PRIORITY 3 [ TICKS 1 ALLOT 1 TIME 2 (of 200) ]
[ time 249 ] IO_START by JOB 0
IO DONE
[ time 249 ] Run JOB 1 at PRIORITY 2 [ TICKS 6 ALLOT 1 TIME 148 (of 200) ]
[ time 250 ] IO_DONE by JOB 0
[ time 250 ] Run JOB 0 at PRIORITY 3 [ TICKS 9 ALLOT 1 TIME 1 (of 200) ]
[ time 251 ] Run JOB 0 at PRIORITY 3 [ TICKS 8 ALLOT 1 TIME 0 (of 200) ]
[ time 252 ] FINISHED JOB 0
[ time 252 ] Run JOB 1 at PRIORITY 2 [ TICKS 5 ALLOT 1 TIME 147 (of 200) ]
[ time 253 ] Run JOB 1 at PRIORITY 2 [ TICKS 4 ALLOT 1 TIME 146 (of 200) ]
[ time 254 ] Run JOB 1 at PRIORITY 2 [ TICKS 3 ALLOT 1 TIME 145 (of 200) ]
[ time 255 ] Run JOB 1 at PRIORITY 2 [ TICKS 2 ALLOT 1 TIME 144 (of 200) ]
[ time 256 ] Run JOB 1 at PRIORITY 2 [ TICKS 1 ALLOT 1 TIME 143 (of 200) ]
[ time 257 ] Run JOB 1 at PRIORITY 2 [ TICKS 0 ALLOT 1 TIME 142 (of 200) ]
[ time 258 ] Run JOB 1 at PRIORITY 1 [ TICKS 9 ALLOT 1 TIME 141 (of 200) ]
[ time 259 ] Run JOB 1 at PRIORITY 1 [ TICKS 8 ALLOT 1 TIME 140 (of 200) ]
[ time 260 ] Run JOB 1 at PRIORITY 1 [ TICKS 7 ALLOT 1 TIME 139 (of 200) ]
[ time 261 ] Run JOB 1 at PRIORITY 1 [ TICKS 6 ALLOT 1 TIME 138 (of 200) ]
[ time 262 ] Run JOB 1 at PRIORITY 1 [ TICKS 5 ALLOT 1 TIME 137 (of 200) ]
[ time 263 ] Run JOB 1 at PRIORITY 1 [ TICKS 4 ALLOT 1 TIME 136 (of 200) ]
[ time 264 ] Run JOB 1 at PRIORITY 1 [ TICKS 3 ALLOT 1 TIME 135 (of 200) ]
[ time 265 ] Run JOB 1 at PRIORITY 1 [ TICKS 2 ALLOT 1 TIME 134 (of 200) ]
[ time 266 ] Run JOB 1 at PRIORITY 1 [ TICKS 1 ALLOT 1 TIME 133 (of 200) ]
[ time 267 ] Run JOB 1 at PRIORITY 1 [ TICKS 0 ALLOT 1 TIME 132 (of 200) ]
[ time 268 ] Run JOB 1 at PRIORITY 0 [ TICKS 9 ALLOT 1 TIME 131 (of 200) ]
[ time 269 ] Run JOB 1 at PRIORITY 0 [ TICKS 8 ALLOT 1 TIME 130 (of 200) ]
[ time 270 ] Run JOB 1 at PRIORITY 0 [ TICKS 7 ALLOT 1 TIME 129 (of 200) ]
[ time 271 ] Run JOB 1 at PRIORITY 0 [ TICKS 6 ALLOT 1 TIME 128 (of 200) ]
[ time 272 ] Run JOB 1 at PRIORITY 0 [ TICKS 5 ALLOT 1 TIME 127 (of 200) ]
[ time 273 ] Run JOB 1 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 126 (of 200) ]
[ time 274 ] Run JOB 1 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 125 (of 200) ]
[ time 275 ] Run JOB 1 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 124 (of 200) ]
[ time 276 ] Run JOB 1 at PRIORITY 0 [ TICKS 1 ALLOT 1 TIME 123 (of 200) ]
[ time 277 ] Run JOB 1 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 122 (of 200) ]
[ time 278 ] Run JOB 1 at PRIORITY 0 [ TICKS 9 ALLOT 1 TIME 121 (of 200) ]
[ time 279 ] Run JOB 1 at PRIORITY 0 [ TICKS 8 ALLOT 1 TIME 120 (of 200) ]
[ time 280 ] Run JOB 1 at PRIORITY 0 [ TICKS 7 ALLOT 1 TIME 119 (of 200) ]
[ time 281 ] Run JOB 1 at PRIORITY 0 [ TICKS 6 ALLOT 1 TIME 118 (of 200) ]
[ time 282 ] Run JOB 1 at PRIORITY 0 [ TICKS 5 ALLOT 1 TIME 117 (of 200) ]
[ time 283 ] Run JOB 1 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 116 (of 200) ]
[ time 284 ] Run JOB 1 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 115 (of 200) ]
[ time 285 ] Run JOB 1 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 114 (of 200) ]
[ time 286 ] Run JOB 1 at PRIORITY 0 [ TICKS 1 ALLOT 1 TIME 113 (of 200) ]
[ time 287 ] Run JOB 1 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 112 (of 200) ]
[ time 288 ] Run JOB 1 at PRIORITY 0 [ TICKS 9 ALLOT 1 TIME 111 (of 200) ]
[ time 289 ] Run JOB 1 at PRIORITY 0 [ TICKS 8 ALLOT 1 TIME 110 (of 200) ]
[ time 290 ] Run JOB 1 at PRIORITY 0 [ TICKS 7 ALLOT 1 TIME 109 (of 200) ]
[ time 291 ] Run JOB 1 at PRIORITY 0 [ TICKS 6 ALLOT 1 TIME 108 (of 200) ]
[ time 292 ] Run JOB 1 at PRIORITY 0 [ TICKS 5 ALLOT 1 TIME 107 (of 200) ]
[ time 293 ] Run JOB 1 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 106 (of 200) ]
[ time 294 ] Run JOB 1 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 105 (of 200) ]
[ time 295 ] Run JOB 1 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 104 (of 200) ]
[ time 296 ] Run JOB 1 at PRIORITY 0 [ TICKS 1 ALLOT 1 TIME 103 (of 200) ]
[ time 297 ] Run JOB 1 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 102 (of 200) ]
[ time 298 ] Run JOB 1 at PRIORITY 0 [ TICKS 9 ALLOT 1 TIME 101 (of 200) ]
[ time 299 ] Run JOB 1 at PRIORITY 0 [ TICKS 8 ALLOT 1 TIME 100 (of 200) ]
[ time 300 ] BOOST ( every 100 )
[ time 300 ] Run JOB 1 at PRIORITY 4 [ TICKS 0 ALLOT 1 TIME 99 (of 200) ]
[ time 301 ] Run JOB 1 at PRIORITY 3 [ TICKS 9 ALLOT 1 TIME 98 (of 200) ]
[ time 302 ] Run JOB 1 at PRIORITY 3 [ TICKS 8 ALLOT 1 TIME 97 (of 200) ]
[ time 303 ] Run JOB 1 at PRIORITY 3 [ TICKS 7 ALLOT 1 TIME 96 (of 200) ]
[ time 304 ] Run JOB 1 at PRIORITY 3 [ TICKS 6 ALLOT 1 TIME 95 (of 200) ]
[ time 305 ] Run JOB 1 at PRIORITY 3 [ TICKS 5 ALLOT 1 TIME 94 (of 200) ]
[ time 306 ] Run JOB 1 at PRIORITY 3 [ TICKS 4 ALLOT 1 TIME 93 (of 200) ]
[ time 307 ] Run JOB 1 at PRIORITY 3 [ TICKS 3 ALLOT 1 TIME 92 (of 200) ]
[ time 308 ] Run JOB 1 at PRIORITY 3 [ TICKS 2 ALLOT 1 TIME 91 (of 200) ]
[ time 309 ] Run JOB 1 at PRIORITY 3 [ TICKS 1 ALLOT 1 TIME 90 (of 200) ]
[ time 310 ] Run JOB 1 at PRIORITY 3 [ TICKS 0 ALLOT 1 TIME 89 (of 200) ]
[ time 311 ] Run JOB 1 at PRIORITY 2 [ TICKS 9 ALLOT 1 TIME 88 (of 200) ]
[ time 312 ] Run JOB 1 at PRIORITY 2 [ TICKS 8 ALLOT 1 TIME 87 (of 200) ]
[ time 313 ] Run JOB 1 at PRIORITY 2 [ TICKS 7 ALLOT 1 TIME 86 (of 200) ]
[ time 314 ] Run JOB 1 at PRIORITY 2 [ TICKS 6 ALLOT 1 TIME 85 (of 200) ]
[ time 315 ] Run JOB 1 at PRIORITY 2 [ TICKS 5 ALLOT 1 TIME 84 (of 200) ]
[ time 316 ] Run JOB 1 at PRIORITY 2 [ TICKS 4 ALLOT 1 TIME 83 (of 200) ]
[ time 317 ] Run JOB 1 at PRIORITY 2 [ TICKS 3 ALLOT 1 TIME 82 (of 200) ]
[ time 318 ] Run JOB 1 at PRIORITY 2 [ TICKS 2 ALLOT 1 TIME 81 (of 200) ]
[ time 319 ] Run JOB 1 at PRIORITY 2 [ TICKS 1 ALLOT 1 TIME 80 (of 200) ]
[ time 320 ] Run JOB 1 at PRIORITY 2 [ TICKS 0 ALLOT 1 TIME 79 (of 200) ]
[ time 321 ] Run JOB 1 at PRIORITY 1 [ TICKS 9 ALLOT 1 TIME 78 (of 200) ]
[ time 322 ] Run JOB 1 at PRIORITY 1 [ TICKS 8 ALLOT 1 TIME 77 (of 200) ]
[ time 323 ] Run JOB 1 at PRIORITY 1 [ TICKS 7 ALLOT 1 TIME 76 (of 200) ]
[ time 324 ] Run JOB 1 at PRIORITY 1 [ TICKS 6 ALLOT 1 TIME 75 (of 200) ]
[ time 325 ] Run JOB 1 at PRIORITY 1 [ TICKS 5 ALLOT 1 TIME 74 (of 200) ]
[ time 326 ] Run JOB 1 at PRIORITY 1 [ TICKS 4 ALLOT 1 TIME 73 (of 200) ]
[ time 327 ] Run JOB 1 at PRIORITY 1 [ TICKS 3 ALLOT 1 TIME 72 (of 200) ]
[ time 328 ] Run JOB 1 at PRIORITY 1 [ TICKS 2 ALLOT 1 TIME 71 (of 200) ]
[ time 329 ] Run JOB 1 at PRIORITY 1 [ TICKS 1 ALLOT 1 TIME 70 (of 200) ]
[ time 330 ] Run JOB 1 at PRIORITY 1 [ TICKS 0 ALLOT 1 TIME 69 (of 200) ]
[ time 331 ] Run JOB 1 at PRIORITY 0 [ TICKS 9 ALLOT 1 TIME 68 (of 200) ]
[ time 332 ] Run JOB 1 at PRIORITY 0 [ TICKS 8 ALLOT 1 TIME 67 (of 200) ]
[ time 333 ] Run JOB 1 at PRIORITY 0 [ TICKS 7 ALLOT 1 TIME 66 (of 200) ]
[ time 334 ] Run JOB 1 at PRIORITY 0 [ TICKS 6 ALLOT 1 TIME 65 (of 200) ]
[ time 335 ] Run JOB 1 at PRIORITY 0 [ TICKS 5 ALLOT 1 TIME 64 (of 200) ]
[ time 336 ] Run JOB 1 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 63 (of 200) ]
[ time 337 ] Run JOB 1 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 62 (of 200) ]
[ time 338 ] Run JOB 1 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 61 (of 200) ]
[ time 339 ] Run JOB 1 at PRIORITY 0 [ TICKS 1 ALLOT 1 TIME 60 (of 200) ]
[ time 340 ] Run JOB 1 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 59 (of 200) ]
[ time 341 ] Run JOB 1 at PRIORITY 0 [ TICKS 9 ALLOT 1 TIME 58 (of 200) ]
[ time 342 ] Run JOB 1 at PRIORITY 0 [ TICKS 8 ALLOT 1 TIME 57 (of 200) ]
[ time 343 ] Run JOB 1 at PRIORITY 0 [ TICKS 7 ALLOT 1 TIME 56 (of 200) ]
[ time 344 ] Run JOB 1 at PRIORITY 0 [ TICKS 6 ALLOT 1 TIME 55 (of 200) ]
[ time 345 ] Run JOB 1 at PRIORITY 0 [ TICKS 5 ALLOT 1 TIME 54 (of 200) ]
[ time 346 ] Run JOB 1 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 53 (of 200) ]
[ time 347 ] Run JOB 1 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 52 (of 200) ]
[ time 348 ] Run JOB 1 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 51 (of 200) ]
[ time 349 ] Run JOB 1 at PRIORITY 0 [ TICKS 1 ALLOT 1 TIME 50 (of 200) ]
[ time 350 ] Run JOB 1 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 49 (of 200) ]
[ time 351 ] Run JOB 1 at PRIORITY 0 [ TICKS 9 ALLOT 1 TIME 48 (of 200) ]
[ time 352 ] Run JOB 1 at PRIORITY 0 [ TICKS 8 ALLOT 1 TIME 47 (of 200) ]
[ time 353 ] Run JOB 1 at PRIORITY 0 [ TICKS 7 ALLOT 1 TIME 46 (of 200) ]
[ time 354 ] Run JOB 1 at PRIORITY 0 [ TICKS 6 ALLOT 1 TIME 45 (of 200) ]
[ time 355 ] Run JOB 1 at PRIORITY 0 [ TICKS 5 ALLOT 1 TIME 44 (of 200) ]
[ time 356 ] Run JOB 1 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 43 (of 200) ]
[ time 357 ] Run JOB 1 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 42 (of 200) ]
[ time 358 ] Run JOB 1 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 41 (of 200) ]
[ time 359 ] Run JOB 1 at PRIORITY 0 [ TICKS 1 ALLOT 1 TIME 40 (of 200) ]
[ time 360 ] Run JOB 1 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 39 (of 200) ]
[ time 361 ] Run JOB 1 at PRIORITY 0 [ TICKS 9 ALLOT 1 TIME 38 (of 200) ]
[ time 362 ] Run JOB 1 at PRIORITY 0 [ TICKS 8 ALLOT 1 TIME 37 (of 200) ]
[ time 363 ] Run JOB 1 at PRIORITY 0 [ TICKS 7 ALLOT 1 TIME 36 (of 200) ]
[ time 364 ] Run JOB 1 at PRIORITY 0 [ TICKS 6 ALLOT 1 TIME 35 (of 200) ]
[ time 365 ] Run JOB 1 at PRIORITY 0 [ TICKS 5 ALLOT 1 TIME 34 (of 200) ]
[ time 366 ] Run JOB 1 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 33 (of 200) ]
[ time 367 ] Run JOB 1 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 32 (of 200) ]
[ time 368 ] Run JOB 1 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 31 (of 200) ]
[ time 369 ] Run JOB 1 at PRIORITY 0 [ TICKS 1 ALLOT 1 TIME 30 (of 200) ]
[ time 370 ] Run JOB 1 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 29 (of 200) ]
[ time 371 ] Run JOB 1 at PRIORITY 0 [ TICKS 9 ALLOT 1 TIME 28 (of 200) ]
[ time 372 ] Run JOB 1 at PRIORITY 0 [ TICKS 8 ALLOT 1 TIME 27 (of 200) ]
[ time 373 ] Run JOB 1 at PRIORITY 0 [ TICKS 7 ALLOT 1 TIME 26 (of 200) ]
[ time 374 ] Run JOB 1 at PRIORITY 0 [ TICKS 6 ALLOT 1 TIME 25 (of 200) ]
[ time 375 ] Run JOB 1 at PRIORITY 0 [ TICKS 5 ALLOT 1 TIME 24 (of 200) ]
[ time 376 ] Run JOB 1 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 23 (of 200) ]
[ time 377 ] Run JOB 1 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 22 (of 200) ]
[ time 378 ] Run JOB 1 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 21 (of 200) ]
[ time 379 ] Run JOB 1 at PRIORITY 0 [ TICKS 1 ALLOT 1 TIME 20 (of 200) ]
[ time 380 ] Run JOB 1 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 19 (of 200) ]
[ time 381 ] Run JOB 1 at PRIORITY 0 [ TICKS 9 ALLOT 1 TIME 18 (of 200) ]
[ time 382 ] Run JOB 1 at PRIORITY 0 [ TICKS 8 ALLOT 1 TIME 17 (of 200) ]
[ time 383 ] Run JOB 1 at PRIORITY 0 [ TICKS 7 ALLOT 1 TIME 16 (of 200) ]
[ time 384 ] Run JOB 1 at PRIORITY 0 [ TICKS 6 ALLOT 1 TIME 15 (of 200) ]
[ time 385 ] Run JOB 1 at PRIORITY 0 [ TICKS 5 ALLOT 1 TIME 14 (of 200) ]
[ time 386 ] Run JOB 1 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 13 (of 200) ]
[ time 387 ] Run JOB 1 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 12 (of 200) ]
[ time 388 ] Run JOB 1 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 11 (of 200) ]
[ time 389 ] Run JOB 1 at PRIORITY 0 [ TICKS 1 ALLOT 1 TIME 10 (of 200) ]
[ time 390 ] Run JOB 1 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 9 (of 200) ]
[ time 391 ] Run JOB 1 at PRIORITY 0 [ TICKS 9 ALLOT 1 TIME 8 (of 200) ]
[ time 392 ] Run JOB 1 at PRIORITY 0 [ TICKS 8 ALLOT 1 TIME 7 (of 200) ]
[ time 393 ] Run JOB 1 at PRIORITY 0 [ TICKS 7 ALLOT 1 TIME 6 (of 200) ]
[ time 394 ] Run JOB 1 at PRIORITY 0 [ TICKS 6 ALLOT 1 TIME 5 (of 200) ]
[ time 395 ] Run JOB 1 at PRIORITY 0 [ TICKS 5 ALLOT 1 TIME 4 (of 200) ]
[ time 396 ] Run JOB 1 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 3 (of 200) ]
[ time 397 ] Run JOB 1 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 2 (of 200) ]
[ time 398 ] Run JOB 1 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 1 (of 200) ]
[ time 399 ] Run JOB 1 at PRIORITY 0 [ TICKS 1 ALLOT 1 TIME 0 (of 200) ]
[ time 400 ] FINISHED JOB 1
```

**6．调度中有一个问题，即刚完成 I/O 的作业添加在队列的哪一端。-I 标志改变了这个调度模拟器的这方面行为。尝试一些工作负载，看看你是否能看到这个标志的效果。**

