---
created: 2024-08-11 13:00
tags:
  - review
  - sort
  - "#On2"
Parent Topic:
  - "[[Arrays]]"
Related Topics:
  - "[[Quick Sort]]"
  - "[[Selection Sort]]"
  - "[[Merge Sort]]"
---
***
### What is Bubble sort
?
It is also called **Sinking Sort.**
- While applying this algorithm the largest element tends to sink to the bottom of the array.
- It repeatedly compares two adjacent elements and swap them if they are in wrong order.
```java
public class bsort {  
    public static void bubbleSort(int[] array) {  
        int n = array.length;  
        for(int i = 0; i < n - 1; i++) {  
            for(int j = 0; j < n - i - 1; j++) {  
                if(array[j + 1] < array[j]) {  
                    int temp = array[j];  
                    array[j] = array[j + 1];  
                    array[j + 1] = temp;  
                }  
            }  
        }  
  
    }  
  
    public static void main(String[] args) {  
        int[] array = {6,5,445,64,6864,0,1};  
        bubbleSort(array);  
  
        for(int a : array) {  
            System.out.print(a + " ");  
        }  
    }  
}
```
<!--SR:!2024-08-28,10,270-->

---
### Generic Method

```java
    public void bubSort(T[] t) {  
        int n = t.length; // Get the length of the array  
        // Outer loop to traverse the array        for (int i = 0; i < n; i++) {  
            // Inner loop to compare adjacent elements  
            for (int j = 0; j < n - 1 - i; j++) {  
                // Compare the current element with the next element  
                if (t[j + 1].compareTo(t[j]) < 0) {  
                    // Swap if the current element is greater than the next element  
                    T temp = t[j];  
                    t[j] = t[j + 1];  
                    t[j + 1] = temp;  
                }  
            }  
        }  
        // Print the sorted array  
        printArray(t);  
    }  
  
    // Method to print the elements of the array  
    public void printArray(T[] t) {  
        for (T a : t) {  
            System.out.print(a + " "); // Print each element followed by a space  
        }  
        System.out.println(); // Print a newline at the end  
    }  
  
    // Main method to test the Bubble Sort implementation  
    public static void main(String[] args) {  
        bubbleSort<Integer> bs = new bubbleSort<>(); // Create an instance of bubbleSort for Integer type  
  
        bs.bubSort(new Integer[]{6, 5, 3, 80, 97, 79, 0}); // Call the bubble sort method with an array of Integers  
    }  
}
```

---
## Bubble sort complexity

Now, let's see the time complexity of bubble sort in the best case, average case, and worst case. We will also see the space complexity of bubble sort.

### 1. Time Complexity Of Bubble Sort

| Case             | Time Complexity |
| ---------------- | --------------- |
| **Best Case**    | O(n)            |
| **Average Case** | O(n2)           |
| **Worst Case**   | O(n2)           |

- **Best Case Complexity for Bubble Sort -** ::It occurs when there is no sorting required, i.e. the array is already sorted. The best-case time complexity of bubble sort is **O(n).**
<!--SR:!2024-08-27,9,250-->
- **Average Case Complexity of Bubble Sort-** ::It occurs when the array elements are in jumbled order that is not properly ascending and not properly descending. The average case time complexity of bubble sort is **O(n2).**
<!--SR:!2024-08-29,11,270-->
- **Worst Case Complexity of Bubble Sort -** ::It occurs when the array elements are required to be sorted in reverse order. That means suppose you have to sort the array elements in ascending order, but its elements are in descending order. The worst-case time complexity of bubble sort is **O(n2).**
<!--SR:!2024-08-31,13,270-->

### 2. Space Complexity

|   |   |
|---|---|
|**Space Complexity**|O(1)|
|**Stable**|YES|

- The space complexity of bubble sort is O(1). It is because, in bubble sort, an extra variable is required for swapping.
- The space complexity of optimized bubble sort is O(2). It is because two extra variables are required in optimized bubble sort.