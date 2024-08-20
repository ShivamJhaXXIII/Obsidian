---
created: 2024-08-14 12:26
tags:
  - sort
  - Onlogn
Parent Topic:
  - "[[Recursion]]"
Related Topics:
  - "[[Bubble Sort]]"
  - "[[Merge Sort]]"
  - "[[Selection Sort]]"
---
***
## How Quick Sort works:
?
- Quick sort is a #divideandconquer algorithm. It involves 3 steps-
	- #### Pivot Selection :
		- We pick an element and mark it as pivot. The pivot element can be first element, last element or any random element.
	- #### Partitioning :
		- We reorder the array such that all the smaller elements are **left to the pivot** and the larger element are to the **right of the pivot**
	- #### Recursion :
		- Recursively apply the above steps on the subarray formed to the left side of the pivot and on the subarray formed at the right side of the pivot.
<!--SR:!2024-08-29,11,270-->

---
### Implementation of Quick Sort
?
```java
int partition(int[] arr, int low, int high) {
	int pivot = arr[high];
	int i = low;
	int j = low;
	while(i <= high) {
		if(arr[i] <= pivot) {
			int temp = arr[i];
			arr[i] = arr[j];
			arr[j] = temp;
			j++;
		}
	i++;
	}
	return j - 1;
}
void sort(int[] arr, int low, int high) {
	if(low < high) {
		int p = partition(arr, low, high);
		sort(arr, low, p-1);
		sort(arr, p + 1, high);
	}
}
```
<!--SR:!2024-08-21,1,210-->

---
### 1. Time Complexity

|Case|Time Complexity|
|---|---|
|**Best Case**|O(n*logn)|
|**Average Case**|O(n*logn)|
|**Worst Case**|O(n2)|

- **Best Case Complexity of Quick Sort-** ::In Quicksort, the best-case occurs when the pivot element is the middle element or near to the middle element. The best-case time complexity of quicksort is **O(n*logn)**.
<!--SR:!2024-08-30,12,270-->
- **Average Case Complexity of Quick Sort-** ::It occurs when the array elements are in jumbled order that is not properly ascending and not properly descending. The average case time complexity of quicksort is **O(n*logn)**.
<!--SR:!2024-08-28,10,270-->
- **Worst Case Complexity of Quick Sort-** ::In quick sort, worst case occurs when the pivot element is either greatest or smallest element. Suppose, if the pivot element is always the last element of the array, the worst case would occur when the given array is sorted already in ascending or descending order. The worst-case time complexity of quicksort is **O(n2)**.
<!--SR:!2024-08-30,12,270-->

Though the worst-case complexity of quicksort is more than other sorting algorithms such as **Merge sort** and **Heap sort**, still it is faster in practice. Worst case in quick sort rarely occurs because by changing the choice of pivot, it can be implemented in different ways. Worst case in quicksort can be avoided by choosing the right pivot element.

### 2. Space Complexity

|   |   |
|---|---|
|**Space Complexity**|O(n*logn)|
|**Stable**|NO|

- The space complexity of quicksort is ::O(n*logn).
<!--SR:!2024-08-27,9,270-->