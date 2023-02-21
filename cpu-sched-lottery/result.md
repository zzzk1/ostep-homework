**问题**
**1．计算 3 个工作在随机种子为 1、2 和 3 时的模拟解。**

```sh
./lottery.py -j 3 -s (1,2,3) -c
```

**2．现在运行两个具体的工作：每个长度为 10，但是一个（工作 0）只有一张彩票，另一个（工作 1）有 100 张（−l 10∶1,10∶100）。彩票数量如此不平衡时会发生什么？在工作 1 完成之前，工作 0 是否会运行？多久？一般来说，这种彩票不平衡对彩票调度的行为有什么影响？**

```sh
./lottery.py -l 10:1,10:100 -c
--> JOB 1 DONE at time 10
--> JOB 0 DONE at time 20
job0未运行
Random 844422 -> Winning ticket 62 (of 101) -> Run 1
  Jobs:
 (  job:0 timeleft:10 tix:1 )  (* job:1 timeleft:10 tix:100 ) 
Random 757955 -> Winning ticket 51 (of 101) -> Run 1
  Jobs:
 (  job:0 timeleft:10 tix:1 )  (* job:1 timeleft:9 tix:100 ) 
Random 420572 -> Winning ticket 8 (of 101) -> Run 1
  Jobs:
 (  job:0 timeleft:10 tix:1 )  (* job:1 timeleft:8 tix:100 ) 
Random 258917 -> Winning ticket 54 (of 101) -> Run 1
  Jobs:
 (  job:0 timeleft:10 tix:1 )  (* job:1 timeleft:7 tix:100 ) 
Random 511275 -> Winning ticket 13 (of 101) -> Run 1
  Jobs:
 (  job:0 timeleft:10 tix:1 )  (* job:1 timeleft:6 tix:100 ) 
Random 404934 -> Winning ticket 25 (of 101) -> Run 1
  Jobs:
 (  job:0 timeleft:10 tix:1 )  (* job:1 timeleft:5 tix:100 ) 
Random 783799 -> Winning ticket 39 (of 101) -> Run 1
  Jobs:
 (  job:0 timeleft:10 tix:1 )  (* job:1 timeleft:4 tix:100 ) 
Random 303313 -> Winning ticket 10 (of 101) -> Run 1
  Jobs:
 (  job:0 timeleft:10 tix:1 )  (* job:1 timeleft:3 tix:100 ) 
Random 476597 -> Winning ticket 79 (of 101) -> Run 1
  Jobs:
 (  job:0 timeleft:10 tix:1 )  (* job:1 timeleft:2 tix:100 ) 
Random 583382 -> Winning ticket 6 (of 101) -> Run 1
  Jobs:
 (  job:0 timeleft:10 tix:1 )  (* job:1 timeleft:1 tix:100 ) 
--> JOB 1 DONE at time 10
```

**3．如果运行两个长度为 100 的工作，都有 100 张彩票（−l100∶100,100∶100），调度程序有多不公平？运行一些不同的随机种子来确定（概率上的）答案。不公平性取决于一项工作比另一项工作早完成多少。**

```sh
./lottery.py -l 100:100,100:100 -c
--> JOB 0 DONE at time 192
--> JOB 1 DONE at time 200
```

**4．随着量子规模（-q）变大，你对上一个问题的答案如何改变？**

```sh
./lottery.py -l 100:100,100:100 -q 10 -c
--> JOB 1 DONE at time 150
--> JOB 0 DONE at time 200
```

```sh
./lottery.py -l 100:100,100:100 -q 20 -c
--> JOB 1 DONE at time 140
--> JOB 0 DONE at time 200
```

```sh
./lottery.py -l 100:100,100:100 -q 30 -c
--> JOB 1 DONE at time 180
--> JOB 0 DONE at time 240
```

```sh
 ./lottery.py -l 100:100,100:100 -q 40 -c
 JOB 1 DONE at time 160
 JOB 0 DONE at time 240
```

```sh
./lottery.py -l 100:100,100:100 -q 50 -c
--> JOB 1 DONE at time 150
--> JOB 0 DONE at time 200
```

```sh
./lottery.py -l 100:100,100:100 -q 60 -c
--> JOB 1 DONE at time 180
--> JOB 0 DONE at time 240
```

**5．你可以制作类似本章中的图表吗？还有什么值得探讨的？用步长调度程序，图表看起来如何？**