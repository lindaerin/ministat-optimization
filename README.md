## Implement a new data structure for inserting new data points

To implement a new data structure for inserting new data points we change the algorithm to use realloc without using calloc or memcpy.

## Implement an_qsort

In the original ministat.c code the final merge sort was implemented using q_sort. In the implementation it is changed to use an_qsort_doubles instead, by including the an_qsort.inc file.

## Implement raw I/O read, write, close

In the code the file descriptor is changed to STDIN_FILENO in order to use read, write,
open, and close and the variable f to an integer value. And a while loop that reads the data.

## Implement Multithreading

Each file was read by multiple threads. A new struct was created named work which holds information about which byte each thread needs to start reading from and where to stop, as well as the file name. The thread uses the read_store function to parse each double in its portion of the file and store it into a new dataset. To retrieve the dataset a dataset pointer was created in the work struct to point at the new dataset. After each thread is done, all the new datasets are appended using the Append function and sorted using qsort. The return value is the sorted array of doubles from the file.

## Implement V Flag

Implement a new option “-v” that emits verbose timing data. The flag v was implemented on the main function of ministat.c and it only set the flag to 1. After the switch statement on the main function, we added an if statement to print out the nanoseconds of the time taken from both the ReadSet function and the Main function. We set clock_monotonic to register the time when each of the functions start and when it finishes running. This time is recorded onto elapsed_us, a function that just subtracts the start time by the end time and adds it to an array t_elap, that will print out the time whenever the compilation asks for the flag -v.

## Strtod_fast

Imported the dtoa library to use the optimized dtoa_fast function.. Replaced strtod with strtod_fast.

# What improved from the baseline?

In the original ministat.c perf report the functions that consumed the most amount of CPU were msort, ReadSet, strtod and dbl_cmp. After the optimization, in comparison to the original ministat.c the final merge sort had less CPU consumption when using an_qsort_doubles. The optimized ministat program also spent less time in the real and user time in comparison to the original ministat.c.
