# CMPS 2200 Reciation 5
## Answers

**Name:**_____Cece Haase & Nicole Davis_________


Place all written answers from `recitation-05.md` here for easier grading.







- **1b.**

Regarding input size, the performance will be based on the distribution of elements in the list. If it is already sorted, it quicksort with fixed pivot might perform faster because it relies on already sorted lists due to it's selection strategy. Quicksort with random sort could face worst-case senarios wheere the randomly chosen pivot partitions the array in an unbalanced way. If its in reverse order, fixed will perform decently well, but it would not work best if the pivot is chosen as the first or last element. Quicksort with random might actually perform better in reverse order as it's less likely to choose the pivot from extreme ends. 

Note that you may have to modify the list sizes based on your system memory; compare at least 10
different list sizes. The `print_results` function in `main.py` gives
a table of results, but feel free to use code from Lab 1 to plot
the results as well. 

Runtimes:
|      n |   qsort-fixed-pivot |   qsort-random-pivot |
|--------|---------------------|----------------------|
|    100 |               0.002 |                0.008 |
|    200 |               0.000 |                0.003 |
|    500 |               0.000 |                0.002 |
|   1000 |               0.000 |                0.002 |
|   2000 |               0.000 |                0.002 |
|   5000 |               0.001 |                0.003 |
|  10000 |               0.001 |                0.004 |
|  20000 |               0.005 |                0.015 |
|  50000 |               0.005 |                0.014 |
| 100000 |               0.005 |                0.016 |





- **1c.**
     n |   timsort |   qsort-fixed-pivot |   qsort-random-pivot |
|--------|-----------|---------------------|----------------------|
|    100 |     0.002 |               0.009 |                0.003 |
|    200 |     0.001 |               0.002 |                0.003 |
|    500 |     0.000 |               0.002 |                0.007 |
|   1000 |     0.010 |               0.003 |                0.012 |
|   2000 |     0.001 |               0.003 |                0.026 |
|   5000 |     0.002 |               0.007 |                0.057 |
|  10000 |     0.002 |               0.008 |                0.113 |
|  20000 |     0.003 |               0.008 |                0.275 |
|  50000 |     0.004 |               0.014 |                0.483 |
| 100000 |     0.004 |               0.013 |                1.003 |

tim sort is the fastest and fixed pivot is on the second fastest as the imput size grows