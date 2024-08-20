---
created: 2024-08-11 11:26
tags:
  - "#search"
  - flashcards
Parent Topic:
  - "[[Arrays]]"
Related Topics:
---
***
### What is Binary Search?
?
Binary search is the search technique that works efficiently on ==sorted lists==. Hence, to search an element into some list using the binary search technique, we must ensure that the list is sorted.
Binary search follows the divide and conquer approach in which the list is divided into two halves, and the item is compared with the middle element of the list. If the match is found then, the location of the middle element is returned. Otherwise, we search into either of the halves depending upon the result produced through the match.

```java   
int low = 0;
int high = array.length - 1;
while(low <= high) {
	int mid = (low + high) / 2;
	if(array[mid] == key) return mid;
	if(key < array[mid]) {
		high = mid - 1;
	} else {
		low = mid + 1;
	}
}
return -1;
```

---
### 1. Time Complexity

|Case|Time Complexity|
|---|---|
|**Best Case**|O(1)|
|**Average Case**|O(logn)|
|**Worst Case**|O(logn)|
- **Best Case Complexity -** In Binary search, best case occurs when the element to search is found in first comparison, i.e., when the first middle element itself is the element to be searched. The best-case time complexity of Binary search is **O(1).**
- **Average Case Complexity -** The average case time complexity of Binary search is **O(logn).**
- **Worst Case Complexity -** In Binary search, the worst case occurs, when we have to keep reducing the search space till it has only one element. The worst-case time complexity of Binary search is **O(logn).**

---
### 2. Space Complexity

| **Space Complexity** | O(1) |
| -------------------- | ---- |
- The space complexity of binary search is O(1).
---

