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
Taking into account NaiveArraySumWorkload, ChunkingArraySumWorkload and NoResultRaceArraySumWorkload, it is possible to observe that chunking the array has the biggest impact on hit ratio. Since threads are dealing with different line-sized portions of data, the hit ratio for L1 cache is significantly improved.  

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

