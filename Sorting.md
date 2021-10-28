## Sorting 
 - Sorting is a fundamental algorithm design problem. Many efficient algorithms
use sorting as a subroutine, because it is often easier to process data if the
elements are in a sorted order

- The efficient general sorting
algorithms work in O(nlogn) time, and many algorithms that use sorting as a
subroutine also have this time complexity.

**O(n^2) algorithms**
1. Bubble sort consists of n rounds. On each round, the algorithm iterates
through the elements of the array. Whenever two consecutive elements are found
that are not in correct order, the algorithm swaps them. The algorithm can be
implemented as follows:

    for (int i = 0; i < n; i++) {
       for (int j = 0; j < n-1; j++) {
          if (array[j] > array[j+1]) {
          swap(array[j],array[j+1]);
           }
        }
    }
    
After the first round of the algorithm, the largest element will be in the correct
position, and in general, after k rounds, the k largest elements will be in the
correct positions. Thus, after n rounds, the whole array will be sorted.

**INVERSIONS**
A useful concept when analyzing sorting algorithms is an inversion: a pair
of array elements (array[a],array[b]) such that a < b and array[a] > array[b], i.e.,
the elements are in the wrong order.

The number of inversions indicates
how much work is needed to sort the array. An array is completely sorted when
there are no inversions. On the other hand, if the array elements are in the
reverse order, the number of inversions is the largest possible:

     1+2+....+(n-1)= [n(n-1)]/2 ==> O(n^2)

Swapping a pair of consecutive elements that are in the wrong order removes
exactly one inversion from the array. Hence, if a sorting algorithm can only swap
consecutive elements, each swap removes at most one inversion, and the time
complexity of the algorithm is at least O(n2).
