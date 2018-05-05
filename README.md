## Sorting

- Types of Sorting
	- Internal : Data to be sorted is small enough to be placed in main memory.
	- External : Large data and can't be placed in main memory(RAM).
- Sort Stability : If algo maintains the relative order of duplicate elements.
- Inplace Sort : When additional space requirement is O(1) i.e. contant. Not directly depend upon the input size.

### Selection Sort

- Simplest techinque
- Selects the smallest element and puts in the first place and then second smallest element and so on.
- Analysis
	- Number of comparison doesn't depend upon the order of the data i.e. not data sensitive.
	- Data in Sorted Order : O(n2).
	- Data in Reverse Order : O(n2).
	- Data in Random Order : O(n2).
- Facts
	- Swaps are very less, only comparisons, as compare to Bubble sort and Insertion sort.
	- For large records selection is better than Bubble and Insertion Sort as cost of moving data is more than comparison for large record.
	- Not Stable.
	- Inplace.

### Bubble Sort

- Compares each element with its adjacent and swaps them if they are not in order.
- Analysis
	- Data in Sorted Order : O(n) assuming we are counting the # of swaps using xchanges in outer loop.
	- Data in Reverse Order : O(n2).
	- Data in Random Order : O(n2).
- Facts
	- Should not be used for large lists due to swaps.
	- Stable sort(maintain the relative order of duplicate elements).
	- Inplace sort(only one temp variable required).
	- Space Complexity : O(1).

### Insertion Sort

- Insertion of the element at proper place like the card player.
- List will be divided into two parts i) Sorted ii) Unsorted.
- Initially sorted part contains only 1 element and rest of the part is unsorted list.
- In each pass first element from the unsorted list is taken and placed in sorted list at proper place.
- Analysis
	- Outer loop will always have n-1 iterations. Iteration of inner loop will vary according to the data.
	- Data in Sorted Order : O(n).
	- Data in Reverse Order : O(n2).
	- Data in Random Order : O(n2).
- Facts
	- Advantage is its simplicity and its very efficient for less elements. As for less elements difference b/w O(nlogn) and O(n2) is very less and O(nlogn) algos are more complex than this algo.
	- We can place a sentinel value at the 0th index and all our data from 1th index. It'll reduce the one if condition in inner loop.
	- We can use the binary search for searching the element but then also we need to shift the elements which will take O(n2). So using binary search will not improve the efficiency of this algo.
	- Disadvantage : of this sorting is number of movements. Elements of the sorted part also move which can be costly in case of large data set in each record.
	- Stable sort(maintain the relative order of duplicate elements).
	- Inplace sort(only one temp variable required).
	- Space Complexity : O(1).

### Merge Sort

- O(nlogn) in both worst and average case.
- Use the merge process, which merges the two sorted arrays in one pass.
- TOP DWON MERGE SORT(RECURSIVE) : Not covering other flavour.
- Analysis
	- n elements repeated divided into half approaximately logn(base 2) times. After halving logn times we get n sublist of size 1.
	- In each pass there will be merging of n elements which is O(n). So the performance of this algo is O(nlogn)
	- Data in Sorted Order : O(nlogn).
	- Data in Reverse Order : O(n2nlogn).
	- Data in Random Order : O(nlogn).
- Facts
	- Stable sort(maintain the relative order of duplicate elements).
	- Not Inplace sort(as merging itself is not inplace).
	- Space Complexity : O(n).

### Quick Sort

### Binary Search Sort

### Heap Sort
    