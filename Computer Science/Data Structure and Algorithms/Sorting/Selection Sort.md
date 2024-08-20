---
created: 2024-08-12 10:19
tags:
  - sort
  - On2
Parent Topic: 
Related Topics:
  - "[[Bubble Sort]]"
  - "[[Merge Sort]]"
  - "[[Quick Sort]]"
---
***
## How Selection sort works:
?
- In selection sort we divide the given array into two parts-sorted part and unsorted part.
- The algorithm sorts an array by repeatedly finding the minimum in an unsorted array and making it part of the sorted array.
<!--SR:!2024-08-21,3,258-->

---
<!--SR:!2024-08-29,11,270-->

## Implementation of Selection sort
### 1.Basic:
?
```java
public void selectSort(int[] array) {
	int n = array.length;
	
	for(int i = 0; i < n - 1; i++) {
		int min = i;
	    for(int j = i + 1; j < n; j++) {
		    if(array[j] < array[min]) {
			    min = j;
		    }
	    }
	    int temp = array[i];
	    array[i] = array[min];
	    array[min] = temp;
	}
}
```
<!--SR:!2024-08-28,10,270-->

### 2.Generic:

```java
public class selectionSort <T extends Comparable<T>> {  
    public void selecSort(T[] a) {  
  
        for(int i = 0; i < a.length - 1; i++) {  
            int minIndex = i;  
            for(int j = i + 1; j < a.length; j++) {  
                if(a[j].compareTo(a[minIndex]) < 0) {  
                    minIndex = j;  
                }  
            }  
            T temp = a[minIndex];  
            a[minIndex] = a[i];  
            a[i] = temp;  
  
        }  
    }  
  
    public void print(T[] a) {  
        for(T e : a) {  
            System.out.print(e + " ");  
        }  
        System.out.println();  
    }  
  
    public static void main(String[] args) {  
        selectionSort<Integer> ss = new selectionSort<>();  
  
        Integer[] a = {5,9,8,6,3,2,7,6};  
  
        ss.selecSort(a);  
        ss.print(a);  
    }  
}
```

---
## Selection sort complexity

Now, let's see the time complexity of selection sort in best case, average case, and in worst case. We will also see the space complexity of the selection sort.

### 1. Time Complexity

|Case|Time Complexity|
|---|---|
|**Best Case**|O(n2)|
|**Average Case**|O(n2)|
|**Worst Case**|O(n2)|

- **Best Case Complexity of Selection Sort-** ::It occurs when there is no sorting required, i.e. the array is already sorted. The best-case time complexity of selection sort is **O(n2)**.
<!--SR:!2024-08-27,9,270-->
- **Average Case Complexity of Selection Sort-** ::It occurs when the array elements are in jumbled order that is not properly ascending and not properly descending. The average case time complexity of selection sort is **O(n2)**.
<!--SR:!2024-08-27,9,270-->
- **Worst Case Complexity of Selection Sort-** ::It occurs when the array elements are required to be sorted in reverse order. That means suppose you have to sort the array elements in ascending order, but its elements are in descending order. The worst-case time complexity of selection sort is **O(n2)**.
<!--SR:!2024-08-28,10,270-->

### 2. Space Complexity

| **Space Complexity** | O(1) |
| -------------------- | ---- |
| **Stable**           | YES  |

- The space complexity of selection sort is ::O(1). It is because, in selection sort, an extra variable is required for swapping.
<!--SR:!2024-08-31,13,270-->