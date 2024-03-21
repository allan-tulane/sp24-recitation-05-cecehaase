# CMPS 2200 Recitation 5

In this recitation, we'll look at randomness in computation.

**To make grading easier, please place all written solutions directly in `answers.md`, rather than scanning in handwritten work or editing this file.**

All coding portions should go in `main.py` as usual.


## Determinism versus Randomization in Quicksort

In lecture we saw that adding a random choice of pivot reduced the
probability of worst-case behavior for any given input in
selection. Let's look at how pivot choices affect Quicksort. For this
question, refer to the code in `main.py` 

**1a)**

Complete the implementations of `qsort` and `compare_sort` stubs. Feel
free to take from code given in the lectures to  help you perform list
partitioning. Note that the pivot choice function is input to `qsort`,
so you will have to curry `qsort` to test different methods of
choosing pivots. Implement variants of `qsort` that correspond to
selecting the first element of the input list as the pivot, and to
selecting a random pivot.
.  
.  
.  
.  


**1b)**

Compare running times using `compare-sort` between variants of
Quicksort and the provided implementation of selection sort (`ssort`). Perform two
different comparisons: a comparison between sorting methods using
random permutations of the specified sizes, and a comparison using
already sorted permutations. 

For quicksort with fixed pivot, it is generally faster, compared to the one with random pivot for all inpt sizes. Given that using a fixed pivot typically leads to a more predictable partitioning of the arry, we avoid worst-case senarios. For quicksort with random pivot, it is slower than with fixed, but preforms relatively well. It shows a slight increase in running time compared to the fixed pivot variant, especially as the input size grows. This is likely due to the randomness which leads to less than optimal partitioning in some cases. 

How does changing the type of input list change the relative performance of these algorithms? 

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



**1c)**

Python uses a sorting algorithm called [*Timsort*](https://en.wikipedia.org/wiki/Timsort), designed by Tim Peters. Compare the fastest of your sorting implementations to the Python
sorting function `sorted`, conducting the tests in 1b above. 


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



