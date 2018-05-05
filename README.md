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
	Number of comparison doesn't depend upon the order of the data i.e. not data sensitive.
	- Data in Sorted Order : O(n).
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
	- Stable sort(maintain the relative order of duplicate elements.)
	- Inplace sort(only one temp variable required)
	- Space Complexity : O(1)

### Insertion Sort

### Quick Sort

### Binary Search Sort

### Heap Sort
    