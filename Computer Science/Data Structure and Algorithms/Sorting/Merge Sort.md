---
created: 2024-08-12 22:17
tags:
  - sort
  - Onlogn
Parent Topic:
  - "[[Recursion]]"
Related Topics:
  - "[[Bubble Sort]]"
  - "[[Quick Sort]]"
  - "[[Selection Sort]]"
---
***
## Explain Merge sort
?
Merge sort is similar to the [[Quick Sort]] algorithm as it uses the #divideandconquer  approach to sort the elements. It is one of the most popular and efficient sorting algorithm. It divides the given list into two equal halves, calls itself for the two halves and then merges the two sorted halves. We have to define the **merge()** function to perform the merging.
The sub-lists are divided again and again into halves until the list cannot be divided further. Then we combine the pair of one element lists into two-element lists, sorting them in the process. The sorted two-element pairs is merged into the four-element lists, and so on until we get the sorted list.
```java
public void mSort(int[] array, int low, int high) {  
    // Base case: If the segment to sort has one or no elements, return
    if(low >= high) {  
        return;  
    }  

    // Find the middle point to divide the array into two halves
    int mid = (low + high) / 2;  

    // Recursively sort the first half
    mSort(array, low, mid);  

    // Recursively sort the second half
    mSort(array, mid + 1, high);  

    // Merge the sorted halves
    merge(array, low, mid, high);  
}  
  
public void merge(int[] array, int low, int mid, int high) {  
    // Create an ArrayList to store the merged result temporarily
    ArrayList<Integer> al = new ArrayList<>();  

	    // Initialize pointers for both halves
    int left = low;  
    int right = mid + 1;  

    // Merge the two halves by comparing elements from both halves
    while(left <= mid && right <= high) {  
        if(array[left] < array[right]) {  
            al.add(array[left]);  // Add the smaller element to the result
            left++;  // Move the pointer of the left half forward
        } else {  
            al.add(array[right]);  // Add the smaller element to the result
            right++;  // Move the pointer of the right half forward
        }  
    }  

    // Copy remaining elements from the left half, if any
    while (left <= mid) {  
        al.add(array[left]);  
        left++;  
    }  

    // Copy remaining elements from the right half, if any
    while (right <= high) {  
        al.add(array[right]);  
        right++;  
    }  

    // Copy the merged elements back into the original array
    for(int i = low; i <= high; i++) {  
        array[i] = al.get(i - low);  
    }  
}

```
<!--SR:!2024-08-25,6,230-->

---
## Merge sort complexity

Now, let's see the time complexity of merge sort in best case, average case, and in worst case. We will also see the space complexity of the merge sort.

### 1. Time Complexity

|Case|Time Complexity|
|---|---|
|**Best Case**|O(n*logn)|
|**Average Case**|O(n*logn)|
|**Worst Case**|O(n*logn)|

- **Best Case Complexity of Merge Sort-** ::It occurs when there is no sorting required, i.e. the array is already sorted. The best-case time complexity of merge sort is **O(n*logn)**.
<!--SR:!2024-08-26,7,268-->
- **Average Case Complexity of Merge Sort-** ::It occurs when the array elements are in jumbled order that is not properly ascending and not properly descending. The average case time complexity of merge sort is **O(n*logn)**.
<!--SR:!2024-08-27,8,268-->
- **Worst Case Complexity of Merge Sort-** ::It occurs when the array elements are required to be sorted in reverse order. That means suppose you have to sort the array elements in ascending order, but its elements are in descending order. The worst-case time complexity of merge sort is **O(n*logn)**.
<!--SR:!2024-08-25,6,268-->

### 2. Space Complexity

|   |   |
|---|---|
|**Space Complexity**|O(n)|
|**Stable**|YES|

- The space complexity of merge sort is ::O(n). It is because, in merge sort, an extra variable is required for swapping.
<!--SR:!2024-08-24,5,248-->