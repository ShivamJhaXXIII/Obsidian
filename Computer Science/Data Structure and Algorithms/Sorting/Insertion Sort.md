---
created: 2024-08-11 16:02
tags:
  - "#sort"
Parent Topic: 
Related Topics:
  - "[[Bubble Sort]]"
---
***
## How Insertion sort works

In Insertion Sort we divide the array into two parts sorted part and unsorted part.

From unsorted part, we take first element and place at its correct position in sorted array. This is done by shifting all the elements which are larger than first element by one position. 

Its repeated till unsorted array is not empty.

```java
public class ISort { // Insertion sort  
    public static void inSort(int[] array) {  
        int n = array.length;  
        for(int i = 1; i < n; i++) {  
            int temp = array[i];  
            int j = i - 1;  
  
            while(j >= 0 && array[j] > temp) {  
                array[j + 1] = array[j];  
                j = j - 1;  
            }  
            array[j + 1] = temp;  
        }  
    }  
  
    public static void main(String[] args) {  
        int[] array = {6,5,445,64,6864,0,1};  
        inSort(array);  
        for(int a : array) {  
            System.out.print(a + " ");  
        }  
    }  
}
```
---
## Insertion sort complexity

Now, let's see the time complexity of insertion sort in best case, average case, and in worst case. We will also see the space complexity of insertion sort.

### 1. Time Complexity

| Case             | Time Complexity |
| ---------------- | --------------- |
| **Best Case**    | O(n)            |
| **Average Case** | O(n2)           |
| **Worst Case**   | O(n2)           |

- **Best Case Complexity -** It occurs when there is no sorting required, i.e. the array is already sorted. The best-case time complexity of insertion sort is **O(n)**.
- **Average Case Complexity -** It occurs when the array elements are in jumbled order that is not properly ascending and not properly descending. The average case time complexity of insertion sort is **O(n2)**.
- **Worst Case Complexity -** It occurs when the array elements are required to be sorted in reverse order. That means suppose you have to sort the array elements in ascending order, but its elements are in descending order. The worst-case time complexity of insertion sort is **O(n2)**.

### 2. Space Complexity

| **Space Complexity** | O(1) |
| -------------------- | ---- |
| **Stable**           | YES  |

- The space complexity of insertion sort is O(1). It is because, in insertion sort, an extra variable is required for swapping.