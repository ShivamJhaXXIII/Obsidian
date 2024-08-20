---
created: 2024-08-14 14:32
tags:
  - sort
Parent Topic: 
Related Topics:
---
***
Problem Statement: Given 0,1 and 2 sort in ascending order.

```java
void threeNumberSort(int[] arr) {
	int i = 0;
	int j = 0;
	int k = arr.length - 1;
	while(i <= k) {
		if(arr[i] == 0) {
			swap(arr,i,j);
			i++;
			j++;
		}
		if(arr[i] == 1) {
			i++;
		}
		if(arr[i] == 2) {
			swap(arr,i,k);
			k--;
		}
	}
}

public void swap(int[] arr, int i, int j) {
	int temp = arr[i];
	arr[i] = arr[j];
	arr[j] = temp;
}
```