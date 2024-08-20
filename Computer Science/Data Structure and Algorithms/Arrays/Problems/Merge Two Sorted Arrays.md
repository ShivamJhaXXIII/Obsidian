---
created: 2024-08-12 10:41
tags:
  - sort
  - Arrays
  - traversal
Parent Topic: 
Related Topics:
---
***
#### Problem Statement: 
Given two Sorted arrays merge them so the resultant array is sorted.

```java
public static int[] merge(int arr1[], int arr2[], int n, int m) {
    // Initialize a result array to hold the merged elements
    int[] result = new int[n + m];
    
    // Initialize pointers for arr1, arr2, and the result array
    int i = 0; 
    int j = 0;
    int k = 0;

    // Traverse both arrays simultaneously and merge them into the result array
	while(i < n && j < m) {
        // If the current element of arr1 is smaller than the current element of arr2
		if(arr1[i] < arr2[j]) {
            // Add the element from arr1 to the result array
			result[k] = arr1[i];
            // Move to the next element in arr1
			i++;  
		} else {
            // Otherwise, add the element from arr2 to the result array
			result[k] = arr2[j];
            // Move to the next element in arr2
			j++;
		}
        // Move to the next position in the result array
		k++;
	}
    
    // Copy any remaining elements from arr1 (if any) to the result array
	while(i < n) {
		result[k] = arr1[i];
		i++;
		k++;
	}
    
    // Copy any remaining elements from arr2 (if any) to the result array
	while(j < m) {
		result[k] = arr2[j];
		j++;
		k++;
	}
    
    // Return the merged array
	return result;
}
```

---
