---
created: 2024-08-17 13:12
tags:
  - Arrays
  - sort
  - Onlogn
  - "#On"
  - "#twoPointers"
Parent Topic: 
Related Topics:
---
***
#### Problem Statement:
Given an Integer Array is in ascending order, return an array of the squares of each number sorted in ascending order

Example:- 
Input array = [-4,-1,0,3,10]
Output - [0,1,9,16,100]

Explanation: After squaring, the array becomes[16,1,0,9,100].
After sorting, it becomes [0,1,9,16,100].

### Two Pointer Method of Sorted Squares:
?
```java
public int[] sortedSquares(int[] arr) {
	int n = arr.length;
	int i = 0, j = n - 1;
	int[] result = new int[n];
	for(int k = n - 1; k >= 0; k++) {
		if(Math.abs(arr[i]) > Msth.abs(arr[j])) {
			result[k] = arr[i] * arr[i];
			i++;
		} else {
			result[k] = arr[j] * arr[j];
			j++;
		}
	}
	return result;
}
```
<!--SR:!2024-08-22,4,270-->

why iterating backwards🚀
1. Since the original array is not sorted, it's not guaranteed 
    that the largest elements (in terms of absolute value) 
    are at the ends of the array.

2. By iterating backwards from the end of the array, we can 
    start populating the result array from the end, ensuring 
    that the squares of larger elements occupy the higher 
    indices of the result array.

#### Complexity

- Time complexity:  
    O(n)
    
- Space complexity:  
    O(n)

---
### Brute Force Method of Sorted Squares:
?
```java
public int[] sortedSquares(int[] nums) {
	int i = 0;
	for(int a : nums) {
		nums[i] = a * a;
		i++;
	}
	Arrays.sort(nums);
	return nums;
}
```
#### Complexity
<!--SR:!2024-08-22,4,270-->

- *Time complexity:  
    O(nlogn)
- *Space complexity:  
    O(1)*
---