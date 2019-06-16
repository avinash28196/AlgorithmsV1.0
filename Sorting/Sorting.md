## Sorting


Two strategy to sort a array

###  Stability In Sorting 
	Sorting algorithm is said to be stable if two objects with equal keys 	appear in the same order in sorted output as they appear in the 	input unsorted array. 

### Example 
Consider a list of pairs: 
```
(1, 2) (9, 7) (3, 4) (8, 6) (9, 3)
```
Now will sort the list using first element of each pair.
#### A stable sorting  outputs :  (1, 2) (3, 4) (8, 6) (9, 7) (9, 3)
Because (9, 3) appears after (9, ￼7) in the original list as well. 

#### An unstable sorting outputs:  (1, 2) (3, 4) (8, 6) (9, 3) (9, 7)

Stable sorts: 
1. Merge sort 
2. Insertion sort 
3. Radix sort 
4. Tim sort 
5. Bubble Sort 


Unstable sorts: 
1. Heap sort 
2. Quick sort 

### In place Sorting.

	A sorting algorithm is in-place if it sorts using only O(1) auxiliary memory (not counting the array that needs to be sorted). 






