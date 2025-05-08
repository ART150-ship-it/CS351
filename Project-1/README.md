# Project #1 Report



## Testing Results
| Program Name | Optimization Level | Real (wall-clock) Time | User Time | System Time | Memory Usage(KB) |   Thorughput    | Performance Improvement|
|--------------|--------------------|------------------------|-----------|-------------|------------------|-----------------|------------------------|
|  hash.00     | None               | 354.22                 | 342.47    | 8.59        | 2896             | 2823 hashes/sec | 1x                     |
|  hash.01     | None               | 19.51                  | 16.34     | 1.94        | 2892             | 51255 hashes/sec| 21x                    |
|  hash.02     | None               | 15.70                  | 14.24     | 1.26        | 2892             | 63694 hashes/sec | 22x                    |
|  hash.03     | None               | 16.47                  | 15.13     | 1.16        | 2900             | 60716 hashes/sec| 21x                    |
|  hash.04     | None               | 14.40                  | 13.73     | 0.56        | 5012372          | 69444 hashes/sec| 24x                    |

| Program Name | Optimization Level | Real (wall-clock) Time | User Time | System Time | Memory Usage(KB) |   Thorughput     | Performance Improvement|
|--------------|--------------------|------------------------|-----------|-------------|------------------|------------------|------------------------|
|  hash.00     | make OPT="-O2"     | 346.25                 | 331.23    | 10.51       | 2880             | 2888 hashes/sec  | 1x                     |
|  hash.01     | make OPT="-O2"     | 12.25                  | 7.29      | 1.82        | 2896             | 81632 hashes/sec | 27x                    |
|  hash.02     | make OPT="-O2"     | 8.42                   | 6.91      | 1.82        | 2896             | 118764 hashes/sec| 41x                    |
|  hash.03     | make OPT="-O2"     | 8.27                   | 6.81      | 1.37        | 2888             | 123918 hashes/sec| 41x                    |
|  hash.04     | make OPT="-O2"     | 7.47                   | 6.73      | 0.54        | 5006032          | 133868 hashes/sec| 46x                    |

| Program Name | Optimization Level | Real (wall-clock) Time | User Time | System Time | Memory Usage(KB) |   Thorughput    | Performance Improvement|
|--------------|--------------------|------------------------|-----------|-------------|------------------|-----------------|------------------------|
|  hash.00     | make OPT="-g"      | 357.37                 | 343.66    | 4.23        | 2900             | 2888 hashes/sec | 1x                     |
|  hash.01     | make OPT="-g"      | 18.05                  | 16.51     | 1.40        | 2900             | 55401 hashes/sec| 19x                    |
|  hash.02     | make OPT="-g"      | 15.73                  | 14.21     | 1.37        | 2888             | 63572 hashes/sec | 22x                    |
|  hash.03     | make OPT="-g"      | 16.50                  | 15.14     | 1.24        | 2880             | 60606 hashes/sec| 21x                    |
|  hash.04     | make OPT="-g"      | 14.54                  | 13.83     | 0.60        | 5011200          | 68775 hashes/sec| 24x                    |

| Program Name | Optimization Level | Real (wall-clock) Time | User Time | System Time | Memory Usage(KB) |   Thorughput     | Performance Improvement|
|--------------|--------------------|------------------------|-----------|-------------|------------------|------------------|------------------------|
|  hash.00     | make OPT="-O3      | 326.68                 | 312.96    | 6.96        | 2896             | 3061 hashes/sec  | 1x                     |
|  hash.01     | make OPT="-O3      | 8.28                   | 6.91      | 1.29        | 3476             | 120772 hashes/sec| 39x                    |
|  hash.02     | make OPT="-O3      | 8.29                   | 6.90      | 1.28        | 3472             | 120627 hashes/sec | 39x                    |
|  hash.03     | make OPT="-O3      | 8.12                   | 6.86      | 1.10        | 2880             | 123152 hashes/sec| 40x                    |
|  hash.04     | make OPT="-O3      | 7.27                   | 6.65      | 0.51        | 5011788          | 137551 hashes/sec| 44x                    |

| Program Name | Optimization Level | Real (wall-clock) Time | User Time | System Time | Memory Usage(KB) |   Thorughput     | Performance Improvement|
|--------------|--------------------|------------------------|-----------|-------------|------------------|------------------|------------------------|
|  hash.00     | make OPT="-Ofast"  | 337.35                 | 329.97    | 4.64        | 2896             | 2964 hashes/sec  | 1x                     |
|  hash.01     | make OPT="-Ofast"  | 7.93                   | 6.73      | 1.12        | 2892             | 126103 hashes/sec| 42x                    |
|  hash.02     | make OPT="-Ofast"  | 7.98                   | 6.82      | 1.10        | 2982             | 125313 hashes/sec | 42x                    |
|  hash.03     | make OPT="-Ofast"  | 8.23                   | 6.84      | 1.3         | 2888             | 121506 hashes/sec| 40x                    |
|  hash.04     | make OPT="-Ofast"  | 7.26                   | 6.64      | 0.53        | 5012352          | 137741 hashes/sec| 46x                    |

## Responses to Questions
1. What operation do you think accounts for most of **hash-00's** runtime?
    1. I think that the operation that is taking most of hash-00 time is maybe the way that it
        reads data into the program, as the other programs read from Data.bin and use .read instead of 
        reading from Data.txt and using input >> byte. 
2. **hash-01** and **hash-02** both dynamically allocate memory for each hash computation.  Is there much difference time-wise between their two allocation methods?
    1. For most of my testing hash-01 and hash-02 seems to have a differnce in time to be about 4
        seconds in real time, but my last two tables seem to have both of them having very simliar times.
        So it would seem that there is a time difference only up to certain optimization levels
3. **hash-03** avoids the allocation by using a fixed-size array.  Is there an appreciable speed difference?
    1. For the no optimization, -O2, and -g it would seem that hash-03 is similar in time with hash-02 so
        there is little speed difference there. But compared to hash-01 it would seem that hash-03 is able to
        have a appreciable speed difference. This trend does disappear when the optimization is turned to
        -O3, or -Ofast as the times for all three of them are very close to each other. 
4. Why is **hash-04's** memory usage so much larger than any of the other versions? Hint: recall when we discussed how the operating system reads a file and makes it available to an application.  Specifically, the O/S will transfer data from disk to its own memory, and then copy from there into buffers provided by the application.  In the memory map case, the O/S is merely sharing the copy of the file's data that is in its (the O/S's) memory, and not making an additional copy from its memory into memory only in the application
    1. Hash-04 uses more memory than the other versions beacuse it mmaps the entire binary file and
        that file is large in size. 
5. What other compiler options did you try, and did they help at all?
    1. Other compiler options that I used were -O3, and -Ofast. It would seem that they helped as the 
        results that I got where faster than -g and similar in time with -O2.
