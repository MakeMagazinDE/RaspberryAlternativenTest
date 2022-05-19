'''
linaro@ASUS-Tinker:~/gpio_lib_python/test$  7z b

7-Zip [32] 16.02 : Copyright (c) 1999-2016 Igor Pavlov : 2016-05-21
p7zip Version 16.02 (locale=C.UTF-8,Utf16=on,HugeFiles=on,32 bits,4 CPUs LE)

LE
CPU Freq:   986  1209  1779  1782  1781  1656  1735  1796  1793

RAM size:    1990 MB,  # CPU hardware threads:   4
RAM usage:    882 MB,  # Benchmark threads:      4

                       Compressing  |                  Decompressing
Dict     Speed Usage    R/U Rating  |      Speed Usage    R/U Rating
         KiB/s     %   MIPS   MIPS  |      KiB/s     %   MIPS   MIPS

22:       3334   333    974   3243  |      79139   391   1727   6752
23:       3366   350    979   3430  |      76908   389   1713   6655
24:       3339   362    991   3591  |      74251   385   1691   6518
25:       3172   364    995   3622  |      71053   381   1661   6324
----------------------------------  | ------------------------------
Avr:             352    985   3472  |              386   1698   6562
Tot:             369   1341   5017


linaro@ASUS-Tinker:~/tinymembench$ ./tinymembench
tinymembench v0.4.9 (simple benchmark for memory throughput and latency)

==========================================================================
== Memory bandwidth tests                                               ==
==                                                                      ==
== Note 1: 1MB = 1000000 bytes                                          ==
== Note 2: Results for 'copy' tests show how many bytes can be          ==
==         copied per second (adding together read and writen           ==
==         bytes would have provided twice higher numbers)              ==
== Note 3: 2-pass copy means that we are using a small temporary buffer ==
==         to first fetch data into it, and only then write it to the   ==
==         destination (source -> L1 cache, L1 cache -> destination)    ==
== Note 4: If sample standard deviation exceeds 0.1%, it is shown in    ==
==         brackets                                                     ==
==========================================================================

 C copy backwards                                     :   2565.4 MB/s (1.1%)
 C copy backwards (32 byte blocks)                    :   2573.6 MB/s (0.8%)
 C copy backwards (64 byte blocks)                    :   2564.0 MB/s (0.9%)
 C copy                                               :   2521.2 MB/s (0.6%)
 C copy prefetched (32 bytes step)                    :   1698.0 MB/s (0.6%)
 C copy prefetched (64 bytes step)                    :   1687.3 MB/s (0.5%)
 C 2-pass copy                                        :   1387.5 MB/s (0.4%)
 C 2-pass copy prefetched (32 bytes step)             :   1145.8 MB/s
 C 2-pass copy prefetched (64 bytes step)             :   1176.2 MB/s (0.6%)
 C fill                                               :   4200.7 MB/s
 C fill (shuffle within 16 byte blocks)               :   4227.7 MB/s (0.3%)
 C fill (shuffle within 32 byte blocks)               :   4212.1 MB/s (0.2%)
 C fill (shuffle within 64 byte blocks)               :   4218.9 MB/s (0.3%)
 ---
 standard memcpy                                      :   1527.7 MB/s (0.3%)
 standard memset                                      :   4211.2 MB/s (0.1%)
 ---
 NEON read                                            :   4997.3 MB/s (0.6%)
 NEON read prefetched (32 bytes step)                 :   4367.1 MB/s (0.5%)
 NEON read prefetched (64 bytes step)                 :   4619.5 MB/s (0.5%)
 NEON read 2 data streams                             :   4360.8 MB/s (0.5%)
 NEON read 2 data streams prefetched (32 bytes step)  :   3745.0 MB/s (0.7%)
 NEON read 2 data streams prefetched (64 bytes step)  :   3770.8 MB/s (0.7%)
 NEON copy                                            :   2511.6 MB/s (1.1%)
 NEON copy prefetched (32 bytes step)                 :   1990.6 MB/s (1.7%)
 NEON copy prefetched (64 bytes step)                 :   1784.1 MB/s (0.6%)
 NEON unrolled copy                                   :   2499.9 MB/s (0.5%)
 NEON unrolled copy prefetched (32 bytes step)        :   2034.7 MB/s (0.8%)
 NEON unrolled copy prefetched (64 bytes step)        :   2433.9 MB/s (1.0%)
 NEON copy backwards                                  :   2570.9 MB/s (1.2%)
 NEON copy backwards prefetched (32 bytes step)       :   2023.5 MB/s (2.6%)
 NEON copy backwards prefetched (64 bytes step)       :   1843.7 MB/s (0.9%)
 NEON 2-pass copy                                     :   1360.9 MB/s (0.3%)
 NEON 2-pass copy prefetched (32 bytes step)          :   1325.0 MB/s
 NEON 2-pass copy prefetched (64 bytes step)          :   1168.8 MB/s (0.1%)
 NEON unrolled 2-pass copy                            :   1368.6 MB/s
 NEON unrolled 2-pass copy prefetched (32 bytes step) :   1331.5 MB/s (0.2%)
 NEON unrolled 2-pass copy prefetched (64 bytes step) :   1386.7 MB/s (0.5%)
 NEON fill                                            :   4225.4 MB/s (0.7%)
 NEON fill backwards                                  :   4217.4 MB/s (0.7%)
 VFP copy                                             :   2495.5 MB/s (1.1%)
 VFP 2-pass copy                                      :   1363.7 MB/s (0.4%)
 ARM fill (STRD)                                      :   4210.3 MB/s
 ARM fill (STM with 8 registers)                      :   4219.1 MB/s (0.3%)
 ARM fill (STM with 4 registers)                      :   4210.9 MB/s (1.2%)
 ARM copy prefetched (incr pld)                       :   2284.6 MB/s (0.5%)
 ARM copy prefetched (wrap pld)                       :   2269.1 MB/s (0.5%)
 ARM 2-pass copy prefetched (incr pld)                :   1365.3 MB/s (0.3%)
 ARM 2-pass copy prefetched (wrap pld)                :   1345.0 MB/s (0.9%)

==========================================================================
== Framebuffer read tests.                                              ==
==                                                                      ==
== Many ARM devices use a part of the system memory as the framebuffer, ==
== typically mapped as uncached but with write-combining enabled.       ==
== Writes to such framebuffers are quite fast, but reads are much       ==
== slower and very sensitive to the alignment and the selection of      ==
== CPU instructions which are used for accessing memory.                ==
==                                                                      ==
== Many x86 systems allocate the framebuffer in the GPU memory,         ==
== accessible for the CPU via a relatively slow PCI-E bus. Moreover,    ==
== PCI-E is asymmetric and handles reads a lot worse than writes.       ==
==                                                                      ==
== If uncached framebuffer reads are reasonably fast (at least 100 MB/s ==
== or preferably >300 MB/s), then using the shadow framebuffer layer    ==
== is not necessary in Xorg DDX drivers, resulting in a nice overall    ==
== performance improvement. For example, the xf86-video-fbturbo DDX     ==
== uses this trick.                                                     ==
==========================================================================

 NEON read (from framebuffer)                         :    803.1 MB/s (1.1%)
 NEON copy (from framebuffer)                         :    320.0 MB/s (1.3%)
 NEON 2-pass copy (from framebuffer)                  :    316.5 MB/s
 NEON unrolled copy (from framebuffer)                :    573.9 MB/s (0.2%)
 NEON 2-pass unrolled copy (from framebuffer)         :    529.4 MB/s (0.3%)
 VFP copy (from framebuffer)                          :    576.2 MB/s (0.3%)
 VFP 2-pass copy (from framebuffer)                   :    528.7 MB/s
 ARM copy (from framebuffer)                          :    345.7 MB/s (0.6%)
 ARM 2-pass copy (from framebuffer)                   :    317.0 MB/s (0.4%)

==========================================================================
== Memory latency test                                                  ==
==                                                                      ==
== Average time is measured for random memory accesses in the buffers   ==
== of different sizes. The larger is the buffer, the more significant   ==
== are relative contributions of TLB, L1/L2 cache misses and SDRAM      ==
== accesses. For extremely large buffer sizes we are expecting to see   ==
== page table walk with several requests to SDRAM for almost every      ==
== memory access (though 64MiB is not nearly large enough to experience ==
== this effect to its fullest).                                         ==
==                                                                      ==
== Note 1: All the numbers are representing extra time, which needs to  ==
==         be added to L1 cache latency. The cycle timings for L1 cache ==
==         latency can be usually found in the processor documentation. ==
== Note 2: Dual random read means that we are simultaneously performing ==
==         two independent memory accesses at a time. In the case if    ==
==         the memory subsystem can't handle multiple outstanding       ==
==         requests, dual random read has the same timings as two       ==
==         single reads performed one after another.                    ==
==========================================================================

block size : single random read / dual random read
      1024 :    0.0 ns          /     0.0 ns
      2048 :    0.0 ns          /     0.0 ns
      4096 :    0.0 ns          /     0.0 ns
      8192 :    0.0 ns          /     0.0 ns
     16384 :    0.0 ns          /     0.0 ns
     32768 :    0.0 ns          /     0.0 ns
     65536 :    7.8 ns          /    13.4 ns
    131072 :   11.8 ns          /    18.8 ns
    262144 :   15.4 ns          /    22.6 ns
    524288 :   17.8 ns          /    25.3 ns
   1048576 :   30.6 ns          /    46.8 ns
   2097152 :   75.5 ns          /   111.7 ns
   4194304 :  101.3 ns          /   138.2 ns
   8388608 :  120.0 ns          /   153.4 ns
  16777216 :  131.0 ns          /   162.4 ns
  33554432 :  139.3 ns          /   170.6 ns
  67108864 :  147.4 ns          /   180.5 ns
linaro@ASUS-Tinker:~/tinymembench$


linaro@ASUS-Tinker:~/tinymembench$ sudo hdparm -t /dev/mmcblk1p8  | grep Timing
 HDIO_DRIVE_CMD(identify) failed: Invalid argument
 Timing buffered disk reads: 384 MB in  3.01 seconds = 127.41 MB/sec
linaro@ASUS-Tinker:~/tinymembench$


linaro@ASUS-Tinker:~$  openssl speed -elapsed aes-128-cbc
You have chosen to measure elapsed time instead of user CPU time.
Doing aes-128 cbc for 3s on 16 size blocks: 14326655 aes-128 cbc's in 3.00s
Doing aes-128 cbc for 3s on 64 size blocks: 3919591 aes-128 cbc's in 3.00s
Doing aes-128 cbc for 3s on 256 size blocks: 1044342 aes-128 cbc's in 3.00s
Doing aes-128 cbc for 3s on 1024 size blocks: 264557 aes-128 cbc's in 3.00s
Doing aes-128 cbc for 3s on 8192 size blocks: 33160 aes-128 cbc's in 3.00s
Doing aes-128 cbc for 3s on 16384 size blocks: 16287 aes-128 cbc's in 3.00s
OpenSSL 1.1.1d  10 Sep 2019
built on: Mon Mar 22 23:08:47 2021 UTC
options:bn(64,32) rc4(char) des(long) aes(partial) blowfish(ptr)
compiler: gcc -fPIC -pthread -Wa,--noexecstack -Wall -Wa,--noexecstack -g -O2 -fdebug-prefix-map=/build/openssl-pp1hfQ/openssl-1.1.1d=. -fstack-protector-strong -Wformat -Werror=format-security -DOPENSSL_USE_NODELETE -DOPENSSL_PIC -DOPENSSL_CPUID_OBJ -DOPENSSL_BN_ASM_MONT -DOPENSSL_BN_ASM_GF2m -DSHA1_ASM -DSHA256_ASM -DSHA512_ASM -DKECCAK1600_ASM -DAES_ASM -DBSAES_ASM -DGHASH_ASM -DECP_NISTZ256_ASM -DPOLY1305_ASM -DNDEBUG -Wdate-time -D_FORTIFY_SOURCE=2
The 'numbers' are in 1000s of bytes per second processed.
type             16 bytes     64 bytes    256 bytes   1024 bytes   8192 bytes  16384 bytes
aes-128 cbc      76408.83k    83617.94k    89117.18k    90302.12k    90548.91k    88948.74k
linaro@ASUS-Tinker:~$


linaro@ASUS-Tinker:~$ sudo hdparm -Tv /dev/mmcblk1p8

/dev/mmcblk1p8:
 HDIO_DRIVE_CMD(identify) failed: Invalid argument
 readonly      =  0 (off)
 readahead     = 256 (on)
 HDIO_DRIVE_CMD(identify) failed: Invalid argument
 geometry      = 471359/4/16, sectors = 30167007, start = 368640
 Timing cached reads:   1650 MB in  2.00 seconds = 824.80 MB/sec
linaro@ASUS-Tinker:~$ sudo hdparm -Tv /dev/mmcblk1p8

/dev/mmcblk1p8:
 HDIO_DRIVE_CMD(identify) failed: Invalid argument
 readonly      =  0 (off)
 readahead     = 256 (on)
 HDIO_DRIVE_CMD(identify) failed: Invalid argument
 geometry      = 471359/4/16, sectors = 30167007, start = 368640
 Timing cached reads:   1662 MB in  2.00 seconds = 831.40 MB/sec
linaro@ASUS-Tinker:~$ sudo hdparm -Tv /dev/mmcblk1p8

/dev/mmcblk1p8:
 HDIO_DRIVE_CMD(identify) failed: Invalid argument
 readonly      =  0 (off)
 readahead     = 256 (on)
 HDIO_DRIVE_CMD(identify) failed: Invalid argument
 geometry      = 471359/4/16, sectors = 30167007, start = 368640
 Timing cached reads:   1690 MB in  2.00 seconds = 845.50 MB/sec
linaro@ASUS-Tinker:~$
'''
