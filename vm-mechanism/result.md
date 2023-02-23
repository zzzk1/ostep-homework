**问题**
**1．用种子 1、2 和 3 运行，并计算进程生成的每个虚拟地址是处于界限内还是界限外?**
**如果在界限内，请计算地址转换。**

```sh
./relocation.py -s 1 -c

ARG seed 1
ARG address space size 1k
ARG phys mem size 16k

Base-and-Bounds register information:

  Base   : 0x0000363c (decimal 13884)
  Limit  : 290

Virtual Address Trace
  VA  0: 0x0000030e (decimal:  782) --> SEGMENTATION VIOLATION
  VA  1: 0x00000105 (decimal:  261) --> VALID: 0x00003741 (decimal: 14145)
  VA  2: 0x000001fb (decimal:  507) --> SEGMENTATION VIOLATION
  VA  3: 0x000001cc (decimal:  460) --> SEGMENTATION VIOLATION
  VA  4: 0x0000029b (decimal:  667) --> SEGMENTATION VIOLATION
```

**2．使用以下标志运行：-s 0 -n 10。为了确保所有生成的虚拟地址都处于边界内，要将**
**-l（界限寄存器）设置为什么值？**

930

```sh
Base-and-Bounds register information:

  Base   : 0x0000360b (decimal 13835)
  Limit  : 929

Virtual Address Trace
  VA  0: 0x00000308 (decimal:  776) --> VALID: 0x00003913 (decimal: 14611)
  VA  1: 0x000001ae (decimal:  430) --> VALID: 0x000037b9 (decimal: 14265)
  VA  2: 0x00000109 (decimal:  265) --> VALID: 0x00003714 (decimal: 14100)
  VA  3: 0x0000020b (decimal:  523) --> VALID: 0x00003816 (decimal: 14358)
  VA  4: 0x0000019e (decimal:  414) --> VALID: 0x000037a9 (decimal: 14249)
  VA  5: 0x00000322 (decimal:  802) --> VALID: 0x0000392d (decimal: 14637)
  VA  6: 0x00000136 (decimal:  310) --> VALID: 0x00003741 (decimal: 14145)
  VA  7: 0x000001e8 (decimal:  488) --> VALID: 0x000037f3 (decimal: 14323)
  VA  8: 0x00000255 (decimal:  597) --> VALID: 0x00003860 (decimal: 14432)
  VA  9: 0x000003a1 (decimal:  929) --> SEGMENTATION VIOLATION
```

```sh
Base-and-Bounds register information:

  Base   : 0x0000360b (decimal 13835)
  Limit  : 930

Virtual Address Trace
  VA  0: 0x00000308 (decimal:  776) --> VALID: 0x00003913 (decimal: 14611)
  VA  1: 0x000001ae (decimal:  430) --> VALID: 0x000037b9 (decimal: 14265)
  VA  2: 0x00000109 (decimal:  265) --> VALID: 0x00003714 (decimal: 14100)
  VA  3: 0x0000020b (decimal:  523) --> VALID: 0x00003816 (decimal: 14358)
  VA  4: 0x0000019e (decimal:  414) --> VALID: 0x000037a9 (decimal: 14249)
  VA  5: 0x00000322 (decimal:  802) --> VALID: 0x0000392d (decimal: 14637)
  VA  6: 0x00000136 (decimal:  310) --> VALID: 0x00003741 (decimal: 14145)
  VA  7: 0x000001e8 (decimal:  488) --> VALID: 0x000037f3 (decimal: 14323)
  VA  8: 0x00000255 (decimal:  597) --> VALID: 0x00003860 (decimal: 14432)
  VA  9: 0x000003a1 (decimal:  929) --> VALID: 0x000039ac (decimal: 14764)
```

**3．使用以下标志运行：-s 1 -n 10 -l 100。可以设置界限的最大值是多少，以便地址空间仍然完全放在物理内存中？**

868

```sh
Base-and-Bounds register information:

  Base   : 0x00000899 (decimal 2201)
  Limit  : 100

Virtual Address Trace
  VA  0: 0x00000363 (decimal:  867) --> SEGMENTATION VIOLATION
  VA  1: 0x0000030e (decimal:  782) --> SEGMENTATION VIOLATION
  VA  2: 0x00000105 (decimal:  261) --> SEGMENTATION VIOLATION
  VA  3: 0x000001fb (decimal:  507) --> SEGMENTATION VIOLATION
  VA  4: 0x000001cc (decimal:  460) --> SEGMENTATION VIOLATION
  VA  5: 0x0000029b (decimal:  667) --> SEGMENTATION VIOLATION
  VA  6: 0x00000327 (decimal:  807) --> SEGMENTATION VIOLATION
  VA  7: 0x00000060 (decimal:   96) --> VALID: 0x000008f9 (decimal: 2297)
  VA  8: 0x0000001d (decimal:   29) --> VALID: 0x000008b6 (decimal: 2230)
  VA  9: 0x00000357 (decimal:  855) --> SEGMENTATION VIOLATION
```

```sh
Base-and-Bounds register information:

  Base   : 0x00000899 (decimal 2201)
  Limit  : 868

Virtual Address Trace
  VA  0: 0x00000363 (decimal:  867) --> VALID: 0x00000bfc (decimal: 3068)
  VA  1: 0x0000030e (decimal:  782) --> VALID: 0x00000ba7 (decimal: 2983)
  VA  2: 0x00000105 (decimal:  261) --> VALID: 0x0000099e (decimal: 2462)
  VA  3: 0x000001fb (decimal:  507) --> VALID: 0x00000a94 (decimal: 2708)
  VA  4: 0x000001cc (decimal:  460) --> VALID: 0x00000a65 (decimal: 2661)
  VA  5: 0x0000029b (decimal:  667) --> VALID: 0x00000b34 (decimal: 2868)
  VA  6: 0x00000327 (decimal:  807) --> VALID: 0x00000bc0 (decimal: 3008)
  VA  7: 0x00000060 (decimal:   96) --> VALID: 0x000008f9 (decimal: 2297)
  VA  8: 0x0000001d (decimal:   29) --> VALID: 0x000008b6 (decimal: 2230)
  VA  9: 0x00000357 (decimal:  855) --> VALID: 0x00000bf0 (decimal: 3056)
```

**4．运行和第 3 题相同的操作，但使用较大的地址空间（-a）和物理内存（-p）。**

```sh
./relocation.py -s 1 -n 10 -l 100 -a 16k -p 32m -c

ARG seed 1
ARG address space size 16k
ARG phys mem size 32m

Base-and-Bounds register information:

  Base   : 0x0044cb63 (decimal 4508515)
  Limit  : 100

Virtual Address Trace
  VA  0: 0x0000363c (decimal: 13884) --> PA or segmentation violation?
  VA  1: 0x000030e1 (decimal: 12513) --> PA or segmentation violation?
  VA  2: 0x00001053 (decimal: 4179) --> PA or segmentation violation?
  VA  3: 0x00001fb5 (decimal: 8117) --> PA or segmentation violation?
  VA  4: 0x00001cc4 (decimal: 7364) --> PA or segmentation violation?
  VA  5: 0x000029b3 (decimal: 10675) --> PA or segmentation violation?
  VA  6: 0x0000327a (decimal: 12922) --> PA or segmentation violation?
  VA  7: 0x00000601 (decimal: 1537) --> PA or segmentation violation?
  VA  8: 0x000001d0 (decimal:  464) --> PA or segmentation violation?
  VA  9: 0x0000357d (decimal: 13693) --> PA or segmentation violation
```

```sh
[root@localhost vm-mechanism]# ./relocation.py -s 1 -n 10 -l 13694 -a 16k -p 32m -c

ARG seed 1
ARG address space size 16k
ARG phys mem size 32m

Base-and-Bounds register information:

  Base   : 0x0044cb63 (decimal 4508515)
  Limit  : 13694

Virtual Address Trace
  VA  0: 0x0000363c (decimal: 13884) --> SEGMENTATION VIOLATION
  VA  1: 0x000030e1 (decimal: 12513) --> VALID: 0x0044fc44 (decimal: 4521028)
  VA  2: 0x00001053 (decimal: 4179) --> VALID: 0x0044dbb6 (decimal: 4512694)
  VA  3: 0x00001fb5 (decimal: 8117) --> VALID: 0x0044eb18 (decimal: 4516632)
  VA  4: 0x00001cc4 (decimal: 7364) --> VALID: 0x0044e827 (decimal: 4515879)
  VA  5: 0x000029b3 (decimal: 10675) --> VALID: 0x0044f516 (decimal: 4519190)
  VA  6: 0x0000327a (decimal: 12922) --> VALID: 0x0044fddd (decimal: 4521437)
  VA  7: 0x00000601 (decimal: 1537) --> VALID: 0x0044d164 (decimal: 4510052)
  VA  8: 0x000001d0 (decimal:  464) --> VALID: 0x0044cd33 (decimal: 4508979)
  VA  9: 0x0000357d (decimal: 13693) --> VALID: 0x004500e0 (decimal: 4522208)
```

**5．作为边界寄存器的值的函数，随机生成的虚拟地址的哪一部分是有效的？画一个图，**
**使用不同随机种子运行，限制值从 0 到最大地址空间大小。**