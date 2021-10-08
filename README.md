## Table of contents
* [General info](#general-info)
* [Technologies](#technologies)
* [Setup](#setup)

## General info
```
The objective of this project is to optimize ministat (a small tool to do the statistics legwork on benchmarks)
```

## Optimization of Ministat 

Goals
```
1. Implement a new data structure for inserting new data points by changing the algorithm to use realloc without using calloc or memcpy
2.  Implement an_qsort by including the an_qsort.inc file
3.  Implement raw I/O read, write, close where file descriptor is changed to STDIN_FILENO in order to use read, write,open, and close
4.  Implement Multithreading where each file is read by multiple threads
5.  Implement V Flag where an implemention of a new option “-v” that emits verbose timing data
6.  Implement Strtod_fast by importing the dtoa library to use the optimized dtoa_fast function.. Replaced strtod with strtod_fast
```

# Original Ministat Perf Report
