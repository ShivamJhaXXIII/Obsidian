---
created: 2024-08-11 11:13
tags:
  - Arrays
  - search
Parent Topic:
  - "[[Arrays]]"
  - "[[Linked List]]"
Related Topics:
---
***
In linear search we traverse through all the elements of data structures and return true if the data is found else we return false.

```java
public int linearSearch(int[] a, int key) {
	for(int i = 0; i < a.length; i++) {
		if (a[i] == key) {
		    retutn i; // returning the index of the key if found
		}
	}
	return -1;
} 
```

---
### Time Complexity:****

- **Best Case:** In the best case, the key might be present at the first index. So the best case complexity is O(1)
- **Worst Case:** In the worst case, the key might be present at the last index i.e., opposite to the end from which the search has started in the list. So the worst-case complexity is O(N) where N is the size of the list.
- **Average Case:** O(N)

**Auxiliary Space:** O(1) as except for the variable to iterate through the list, no other variable is used.

---
### Applications of Linear Search Algorithm:

- ***Unsorted Lists:*** When we have an unsorted array or list, linear search is most commonly used to find any element in the collection.
- **Small Data Sets:** Linear Search is preferred over binary search when we have small data sets with
- **Searching Linked Lists:** In linked list implementations, linear search is commonly used to find elements within the list. Each node is checked sequentially until the desired element is found.
- **Simple Implementation:** Linear Search is much easier to understand and implement as compared to Binary Search or Ternary Search.
---
### Advantages of Linear Search Algorithm:
Linear search can be used irrespective of whether the array is sorted or not. It can be used on arrays of any data type.
- Does not require any additional memory.
- It is a well-suited algorithm for small datasets.
---
### Disadvantages of Linear Search Algorithm:

- Linear search has a time complexity of O(N), which in turn makes it slow for large datasets.
- Not suitable for large arrays.
---
## When to use Linear Search Algorithm?

- When we are dealing with a small dataset.
- When you are searching for a dataset stored in contiguous memory.