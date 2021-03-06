- [MAIN LINK TO FOLLOW](https://www.geeksforgeeks.org/amazon-interview-preparation/)
- [CURRENT LINK TO FOLLW](https://www.cdn.geeksforgeeks.org/must-do-coding-questions-for-companies-like-amazon-microsoft-adobe/)

- [FAQ - 1](https://www.geeksforgeeks.org/amazons-asked-interview-questions/)
- [FAQ - 2](https://www.geeksforgeeks.org/amazons-most-frequently-asked-interview-questions-set-2/)
- [Interview Experience](https://www.geeksforgeeks.org/tag/amazon/)

<details>
<summary>Sorting</summary>

## Sorting

- Types of Sorting
	- Internal : Data to be sorted is small enough to be placed in main memory.
	- External : Large data and can't be placed in main memory(RAM).
- Sort Stability : If algo maintains the relative order of duplicate elements.
- Inplace Sort : When additional space requirement is O(1) i.e. constant. Not directly depend upon the input size.
 
<details>
<summary>Selection Sort</summary>

### Selection Sort

- Simplest techinque
- Selects the smallest element and puts in the first place and then second smallest element and so on.
#### Analysis
- Number of comparison doesn't depend upon the order of the data i.e. not data sensitive.
- Data in Sorted Order : O(n2).
- Data in Reverse Order : O(n2).
- Data in Random Order : O(n2).
#### Facts
- Swaps are very less, only comparisons, as compare to Bubble sort and Insertion sort.
- For large records selection is better than Bubble and Insertion Sort as cost of moving data is more than comparison for large record.
- Not Stable.
- Inplace.
</details>
<details>
<summary>Bubble Sort</summary>

### Bubble Sort

- Compares each element with its adjacent and swaps them if they are not in order.
#### Analysis
- Data in Sorted Order : O(n) assuming we are counting the # of swaps using xchanges in outer loop.
- Data in Reverse Order : O(n2).
- Data in Random Order : O(n2).
#### Facts
- Should not be used for large lists due to swaps.
- Stable sort(maintain the relative order of duplicate elements).
- Inplace sort(only one temp variable required).
- Space Complexity : O(1).
</details>
<details>
<summary>Insertion Sort</summary>

### Insertion Sort

- Insertion of the element at proper place like the card player.
- List will be divided into two parts i) Sorted ii) Unsorted.
- Initially sorted part contains only 1 element and rest of the part is unsorted list.
- In each pass first element from the unsorted list is taken and placed in sorted list at proper place.
#### Analysis
- Outer loop will always have n-1 iterations. Iteration of inner loop will vary according to the data.
- Data in Sorted Order : O(n).
- Data in Reverse Order : O(n2).
- Data in Random Order : O(n2).
#### Facts
- Advantage is its simplicity and its very efficient for less elements. As for less elements difference b/w O(nlogn) and O(n2) is very less and O(nlogn) algos are more complex than this algo.
- We can place a sentinel value at the 0th index and all our data from 1th index. It'll reduce the one if condition in inner loop.
- We can use the binary search for searching the element but then also we need to shift the elements which will take O(n2). So using binary search will not improve the efficiency of this algo.
- Disadvantage : of this sorting is number of movements. Elements of the sorted part also move which can be costly in case of large data set in each record.
- Stable sort(maintain the relative order of duplicate elements).
- Inplace sort(only one temp variable required).
- Space Complexity : O(1).
</details>
<details>
<summary>Merge Sort</summary>

### Merge Sort

- O(nlogn) in both worst and average case.
- Use the merge process, which merges the two sorted arrays in one pass.
- TOP DWON MERGE SORT(RECURSIVE) : Not covering other flavour.
#### Analysis
- n elements repeated divided into half approaximately logn(base 2) times. After halving logn times we get n sublist of size 1.
- In each pass there will be merging of n elements which is O(n). So the performance of this algo is O(nlogn)
- Data in Sorted Order : O(nlogn).
- Data in Reverse Order : O(nlogn).
- Data in Random Order : O(nlogn).
#### Facts
- Stable sort(maintain the relative order of duplicate elements).
- Not Inplace sort(as merging itself is not inplace).
- Space Complexity : O(n).
</details>
<details>
<summary>Quick Sort</summary>

### Quick Sort(Partition Exchange Sort)

- Choose the element from the list and place it as its proper position in the list i.e. the final position.
- This element is pivot and
	- all elements to the left are <= the pivot(less than or equal to).
	- all elements to the right are >= the pivot.
- Any element can be pivot but for convenience we choose the first element.
- Sublists of the left and right are sorted recursively using quick_sort algo itself.
- Terminating condition of recursion will be when sublist contains only one element.
- No need to combine the sublist at the end, as they are placed in that way that they are already combined.
#### Algo
- Suppose we have arr[low:up] and arr[low] is pivot. Then i=low+1 and j = up.
- a) : compare the pivot with arr[i], and increment i if arr[i] < pivot. So i moves LTR and stops when we get an element>= pivot.
- b) : compare the pivot with arr[j], and decrement j if arr[j] > pivot. So j moves RTL and stops when we get he element<= pivot.
- c) : if i< j
	- swap arr[i] and arr[j] and i++ and j--.
	- else
		- No swap, i++.
- d) : Repeat a,b,c till the value of i is less than or equal to j. Stop when i exceeds j.
- e) : When i>j then proper place for i pivot is jth index.
#### Analysis
- If the partition is balanced i.e. two sublists are of equal size then sort is fast o/w slow.
- Worst Case : O(n2).
- Average Case : O(nlogn).
- Best Case : O(nlogn).
#### Facts
- Not Stable sort.
- Inplace sort.
- Space Complexity : O(logn). Pivot variable in quick_sort method.
#### Choice of Pivot in Quick Sort
- First element : is not good choice in sorted or almost sorted array as it'll imbalance the sublists.
- Last element : Same as above.
- Random number : Good, but random number generation itself is costly.
- Ideal choice : is median of the elements. So instead of all elements choose median of first,last and mid elements. arr[low],arr[up],arr[(low+up)/2]. **Refer SK Srivastava Page 450. Little Tricky.**
#### Deterministic Selection algorithm of O(n)
- [Also called Median selection algo](https://www.youtube.com/watch?v=eRqmSTSmkJk)
- [Refer-GFG](https://www.geeksforgeeks.org/kth-smallestlargest-element-unsorted-array-set-3-worst-case-linear-time/)
- [Refer](selection-algos/deterministic-selection-algo/median-lineartime.pdf)
- [Refer](selection-algos/deterministic-selection-algo/L05.pdf)
- Algo
	- Divide the elements in the group of 5.
	- Sort the groups.
		- Running time will be O(n). Cause let's say if we use merge sort to sort the array of 5 elements than it will have 6*n*(log5base2 + 1) which will be 6*5*(3+1) = 120.
		- Now there will be n/5 groups in which each group will take 120 operations which will be n/5*120 = 24n. so O(n) total time.
	- Find meadians of each group.
	- Put all the medians in a separate array and find the median of this array. Call this new median, median of median(MOM).
	- This MOM is the pivot element.
	- Now partition using this element as pivot in Quick Sort algo.
#### Duplicate elemnets in Quick Sort
- We stop variables when we find an element equal to the pivot. There can be 4 other options.
	- stop i and move j : All equql elements would go the right sublist.
	- stop j and move i : All equql elements would go the left sublist.
	- stop both i and j : Many unnecessary swaps in case all the elements are same,but good thing is that i and j will meet in middle of the list. So no unbalanced sublists.
	- move both i and j : No unnecessary swaps but unbalanced sublists.
</details>
<details>
<summary>Binary Search Sort</summary>

### Binary Search Sort

</details>
<details>
<summary>Heap Sort</summary>
### Heap Sort
</details>

</details>

<details>
<summary>Searching</summary>
</details>




# References
https://www.youtube.com/watch?v=yRM3sc57q0c&list=PLXFMmlk03Dt7Q0xr1PIAriY5623cKiH7V