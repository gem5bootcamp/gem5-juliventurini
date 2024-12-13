## Question 1:
For algorithm 1:
Mean time for 10 executions using 1 thread was:
2.458245
Mean time for 10 executions using 2 threads was:
2.792961
Mean time for 10 executions using 3 threads was:
2.886288
Mean time for 10 executions using 4 threads was:
2.723286

Therefore, increasing the number of threads does not improve the performance. We could even argue that it worsens it due to the added overhead caused by multiple threads trying to access the same resource simultaneously.

## Question 2:
a)
For algorithm 6:
In this case, increasing the number of threads does improve the performance since each thread writes in different memory blocks and reads from a distinct section of the array, so no racing issues occur. 

b)
The mean time for 10 executions using 1 thread was:
1.409ms
The mean time for 10 executions using 2 threads was:
1.0429089
The mean time for 10 executions using 3 threads was:
0.9803531
The mean time for 10 executions using 4 threads was:
1.0062176

## Question 3:
a)
I think the most effective optimization is padding the result so that each thread handles different blocks. Looking at the results, it seems that algorithm block-race-opt-native is the better improvement out of the ones mentioned, reducing the time of the naive algorithm (aprox 2.5/3 seconds) to about 0.5/0.7 seconds. (Using 4 threads)

b)
I think what could be happening is that the cache does not implement isntant write-back, therefore, since each thread handles a different block in memory, they can work on the whole array without ever having to write to memory to keep caches coherent, thus increasing the efficiency significantly. 

## Question 4:
(Using 4 threads)
Time naive: 0.815248 ms (against 2.723286 ms on real hardware)
Time ChunkingNoBlockRaceArray: 0.238381 ms (against 1.0062176 ms on real hardware)

## Question 5:
NaiveArraySumWorkload:
l1_controllers1.L1Dcache       105731
l1_controllers1.L1Icache       164386
l1_controllers10.L1Dcache            0
l1_controllers10.L1Icache            0
l1_controllers11.L1Dcache            0
l1_controllers11.L1Icache            0
l1_controllers12.L1Dcache            0
l1_controllers12.L1Icache            0
l1_controllers13.L1Dcache            0
l1_controllers13.L1Icache            0
l1_controllers14.L1Dcache            0
l1_controllers14.L1Icache            0
l1_controllers15.L1Dcache            0
l1_controllers15.L1Icache            0
l1_controllers16.L1Dcache            0
l1_controllers16.L1Icache            0
l1_controllers2.L1Dcache       105620
l1_controllers2.L1Icache       164451
l1_controllers3.L1Dcache       105319
l1_controllers3.L1Icache       164428
l1_controllers4.L1Dcache       105374
l1_controllers4.L1Icache       164433
l1_controllers5.L1Dcache            0
l1_controllers5.L1Icache            0
l1_controllers6.L1Dcache            0
l1_controllers6.L1Icache            0
l1_controllers7.L1Dcache            0
l1_controllers7.L1Icache            0
l1_controllers8.L1Dcache            0
l1_controllers8.L1Icache            0
l1_controllers9.L1Dcache            0
l1_controllers9.L1Icache            0
l2_controllers1.L2cache          438
l2_controllers10.L2cache          446
l2_controllers11.L2cache          429
l2_controllers12.L2cache          437
l2_controllers13.L2cache          429
l2_controllers14.L2cache          444
l2_controllers15.L2cache          438
l2_controllers2.L2cache          429
l2_controllers3.L2cache          432
l2_controllers4.L2cache          440
l2_controllers5.L2cache          450
l2_controllers6.L2cache          451
l2_controllers7.L2cache          427
l2_controllers8.L2cache          436
l2_controllers9.L2cache          435
l1_controllers1.L1Dcache       105731
l1_controllers1.L1Icache       164386
l1_controllers10.L1Dcache            0
l1_controllers10.L1Icache            0
l1_controllers11.L1Dcache            0
l1_controllers11.L1Icache            0
l1_controllers12.L1Dcache            0
l1_controllers12.L1Icache            0
l1_controllers13.L1Dcache            0
l1_controllers13.L1Icache            0
l1_controllers14.L1Dcache            0
l1_controllers14.L1Icache            0
l1_controllers15.L1Dcache            0
l1_controllers15.L1Icache            0
l1_controllers16.L1Dcache            0
l1_controllers16.L1Icache            0
l1_controllers2.L1Dcache       105620
l1_controllers2.L1Icache       164451
l1_controllers3.L1Dcache       105319
l1_controllers3.L1Icache       164428
l1_controllers4.L1Dcache       105374
l1_controllers4.L1Icache       164433
l1_controllers5.L1Dcache            0
l1_controllers5.L1Icache            0
l1_controllers6.L1Dcache            0
l1_controllers6.L1Icache            0
l1_controllers7.L1Dcache            0
l1_controllers7.L1Icache            0
l1_controllers8.L1Dcache            0
l1_controllers8.L1Icache            0
l1_controllers9.L1Dcache            0
l1_controllers9.L1Icache            0
l2_controllers1.L2cache          446
l2_controllers10.L2cache          456
l2_controllers11.L2cache          436
l2_controllers12.L2cache          449
l2_controllers13.L2cache          445
l2_controllers14.L2cache          460
l2_controllers15.L2cache          446
l2_controllers2.L2cache          441
l2_controllers3.L2cache          444
l2_controllers4.L2cache          449
l2_controllers5.L2cache          462
l2_controllers6.L2cache          470
l2_controllers7.L2cache          433
l2_controllers8.L2cache          441
l2_controllers9.L2cache          444


ChunkingArraySumWorkload:
l1_controllers1.L1Dcache       123682
l1_controllers1.L1Icache       123445
l1_controllers10.L1Dcache            0
l1_controllers10.L1Icache            0
l1_controllers11.L1Dcache            0
l1_controllers11.L1Icache            0
l1_controllers12.L1Dcache            0
l1_controllers12.L1Icache            0
l1_controllers13.L1Dcache            0
l1_controllers13.L1Icache            0
l1_controllers14.L1Dcache            0
l1_controllers14.L1Icache            0
l1_controllers15.L1Dcache            0
l1_controllers15.L1Icache            0
l1_controllers16.L1Dcache            0
l1_controllers16.L1Icache            0
l1_controllers2.L1Dcache       123565
l1_controllers2.L1Icache       123520
l1_controllers3.L1Dcache       123261
l1_controllers3.L1Icache       123486
l1_controllers4.L1Dcache       123314
l1_controllers4.L1Icache       123499
l1_controllers5.L1Dcache            0
l1_controllers5.L1Icache            0
l1_controllers6.L1Dcache            0
l1_controllers6.L1Icache            0
l1_controllers7.L1Dcache            0
l1_controllers7.L1Icache            0
l1_controllers8.L1Dcache            0
l1_controllers8.L1Icache            0
l1_controllers9.L1Dcache            0
l1_controllers9.L1Icache            0
l2_controllers1.L2cache          159
l2_controllers10.L2cache          173
l2_controllers11.L2cache          151
l2_controllers12.L2cache          162
l2_controllers13.L2cache          157
l2_controllers14.L2cache          166
l2_controllers15.L2cache          155
l2_controllers2.L2cache          152
l2_controllers3.L2cache          156
l2_controllers4.L2cache          160
l2_controllers5.L2cache          177
l2_controllers6.L2cache          175
l2_controllers7.L2cache          148
l2_controllers8.L2cache          159
l2_controllers9.L2cache          160
l1_controllers1.L1Dcache       123682
l1_controllers1.L1Icache       123445
l1_controllers10.L1Dcache            0
l1_controllers10.L1Icache            0
l1_controllers11.L1Dcache            0
l1_controllers11.L1Icache            0
l1_controllers12.L1Dcache            0
l1_controllers12.L1Icache            0
l1_controllers13.L1Dcache            0
l1_controllers13.L1Icache            0
l1_controllers14.L1Dcache            0
l1_controllers14.L1Icache            0
l1_controllers15.L1Dcache            0
l1_controllers15.L1Icache            0
l1_controllers16.L1Dcache            0
l1_controllers16.L1Icache            0
l1_controllers2.L1Dcache       123565
l1_controllers2.L1Icache       123520
l1_controllers3.L1Dcache       123261
l1_controllers3.L1Icache       123486
l1_controllers4.L1Dcache       123314
l1_controllers4.L1Icache       123499
l1_controllers5.L1Dcache            0
l1_controllers5.L1Icache            0
l1_controllers6.L1Dcache            0
l1_controllers6.L1Icache            0
l1_controllers7.L1Dcache            0
l1_controllers7.L1Icache            0
l1_controllers8.L1Dcache            0
l1_controllers8.L1Icache            0
l1_controllers9.L1Dcache            0
l1_controllers9.L1Icache            0
l2_controllers1.L2cache          167
l2_controllers10.L2cache          183
l2_controllers11.L2cache          158
l2_controllers12.L2cache          175
l2_controllers13.L2cache          173
l2_controllers14.L2cache          181
l2_controllers15.L2cache          164
l2_controllers2.L2cache          164
l2_controllers3.L2cache          167
l2_controllers4.L2cache          169
l2_controllers5.L2cache          189
l2_controllers6.L2cache          193
l2_controllers7.L2cache          154
l2_controllers8.L2cache          164
l2_controllers9.L2cache          169

NoResultRaceArraySumWorkload:
l1_controllers1.L1Dcache       113901
l1_controllers1.L1Icache       156192
l1_controllers10.L1Dcache            0
l1_controllers10.L1Icache            0
l1_controllers11.L1Dcache            0
l1_controllers11.L1Icache            0
l1_controllers12.L1Dcache            0
l1_controllers12.L1Icache            0
l1_controllers13.L1Dcache            0
l1_controllers13.L1Icache            0
l1_controllers14.L1Dcache            0
l1_controllers14.L1Icache            0
l1_controllers15.L1Dcache            0
l1_controllers15.L1Icache            0
l1_controllers16.L1Dcache            0
l1_controllers16.L1Icache            0
l1_controllers2.L1Dcache       113792
l1_controllers2.L1Icache       156267
l1_controllers3.L1Dcache       113514
l1_controllers3.L1Icache       156231
l1_controllers4.L1Dcache       113855
l1_controllers4.L1Icache       156268
l1_controllers5.L1Dcache            0
l1_controllers5.L1Icache            0
l1_controllers6.L1Dcache            0
l1_controllers6.L1Icache            0
l1_controllers7.L1Dcache            0
l1_controllers7.L1Icache            0
l1_controllers8.L1Dcache            0
l1_controllers8.L1Icache            0
l1_controllers9.L1Dcache            0
l1_controllers9.L1Icache            0
l2_controllers1.L2cache          442
l2_controllers10.L2cache          447
l2_controllers11.L2cache          434
l2_controllers12.L2cache          441
l2_controllers13.L2cache          432
l2_controllers14.L2cache          446
l2_controllers15.L2cache          440
l2_controllers2.L2cache          428
l2_controllers3.L2cache          435
l2_controllers4.L2cache          442
l2_controllers5.L2cache          451
l2_controllers6.L2cache          450
l2_controllers7.L2cache          423
l2_controllers8.L2cache          434
l2_controllers9.L2cache          437
l1_controllers1.L1Dcache       113901
l1_controllers1.L1Icache       156192
l1_controllers10.L1Dcache            0
l1_controllers10.L1Icache            0
l1_controllers11.L1Dcache            0
l1_controllers11.L1Icache            0
l1_controllers12.L1Dcache            0
l1_controllers12.L1Icache            0
l1_controllers13.L1Dcache            0
l1_controllers13.L1Icache            0
l1_controllers14.L1Dcache            0
l1_controllers14.L1Icache            0
l1_controllers15.L1Dcache            0
l1_controllers15.L1Icache            0
l1_controllers16.L1Dcache            0
l1_controllers16.L1Icache            0
l1_controllers2.L1Dcache       113792
l1_controllers2.L1Icache       156267
l1_controllers3.L1Dcache       113514
l1_controllers3.L1Icache       156231
l1_controllers4.L1Dcache       113855
l1_controllers4.L1Icache       156268
l1_controllers5.L1Dcache            0
l1_controllers5.L1Icache            0
l1_controllers6.L1Dcache            0
l1_controllers6.L1Icache            0
l1_controllers7.L1Dcache            0
l1_controllers7.L1Icache            0
l1_controllers8.L1Dcache            0
l1_controllers8.L1Icache            0
l1_controllers9.L1Dcache            0
l1_controllers9.L1Icache            0
l2_controllers1.L2cache          450
l2_controllers10.L2cache          457
l2_controllers11.L2cache          441
l2_controllers12.L2cache          453
l2_controllers13.L2cache          448
l2_controllers14.L2cache          461
l2_controllers15.L2cache          449
l2_controllers2.L2cache          440
l2_controllers3.L2cache          446
l2_controllers4.L2cache          451
l2_controllers5.L2cache          463
l2_controllers6.L2cache          467
l2_controllers7.L2cache          429
l2_controllers8.L2cache          439
l2_controllers9.L2cache          446


## Question 6: Read Sharing
For testing impact on read sharing, I analized the naive algorithm, the chunking algorithm, res-race algorithm and block-race algorithm.

Demand misses (total in data caches): 
Naive: 82.366 
Chunking: 70.668
Res Race: 82.988
Block Race: 33.374

The most impactful optimization on read sharing is by far block race optimization, which makes sense since threads are never racing over one shared result address. 

## Question 7: Write Sharing
Using the same algorithms as before.
Using demand misses since read and write misses are not differentiated, block race is still the best optimization. 

## Question 8:
The most important metric for determining performance is L1 hit ratio, since it combines read and write sharing information, providing a broader perspective of the overall performance. 
L1 cache size and associativity are the main causes for padding result to be the best optimization.

## Question 9:
Naive:
	Delay:
	1 ---> 0.000347 sim secs
	10 ---> 0.000815 sim secs
	25 ---> 0.000962 sim secs
All Optimizations:
	Delay:
	1 ---> 0.000227 sim secs 
	10 ---> 0.000238 sim secs
	25 ---> 0.000259 sim secs

Its clear to see that with no optimizations, as the crossbar latency increases, the total simulation time increases as well. However with all optimizations, the simulated time is of the same magnitude no matter the crossbar latency.
In conclusion, the optimizations become more important when the latency increases. 

