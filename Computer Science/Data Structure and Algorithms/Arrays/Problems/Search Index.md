---
created: 2024-08-11 12:15
tags:
  - Arrays
  - search
Parent Topic:
  - "[[Arrays]]"
  - "[[Binary Search]]"
Related Topics:
---
***
Problem Statement:
Given a sorted array of distinct Integers and a target value, return the index if the target is found. If not, return the suitable index for it to be inserted.

- The algorithm should run in #Ologn time.

```java
public class searchIndex {  
    public static int search(int[] array, int key) {  
        int low = 0;  
        int high = array.length - 1;  
        int mid = 0;  
        while(low<=high) {  
            mid = low + (high - low) / 2;  // This is to avoid Integer overflow in case of very large array.
            if(array[mid] == key) return mid;  
            if(array[mid] < key) {  
                low = mid + 1;  
            } else {  
                high = mid - 1;  
            }  
        }  
        return low;  
    }  
  
    public static void main(String[] args) {  
        int[] array = {0,1,3,4,6};  
  
        System.out.println(search(array, 7));  
        System.out.println(search(array, 5));  
    }  
}
```