---
created: 2024-08-17 18:49
tags:
  - twoPointers
  - Arrays
  - sort
Parent Topic:
  - "[[Arrays]]"
Related Topics:
---
***
#### Problem Statement:
Given Sorted array of integers, rearrange in such a way that the first position will have the largest number, the second will have the smallest, the third will have the second-largest, and so on.

Example:
Input = [1,2,3,4,5,6,7]
Output = [7,1,6,2,5,3,4]

```java
void arrangeMaxMin(int[] arr) {
    // Initialize indices to track the maximum and minimum elements in the array.
    int maxIdx = arr.length - 1; // Start with the last element (maximum index)
    int minIdx = 0;              // Start with the first element (minimum index)

    // Choose a value greater than the maximum element in the array.
    // This will be used to store both the original and new values in the same index.
    int max = arr[maxIdx] + 1;

    // Traverse the array and modify each element in a way that stores two values:
    // 1. The original value
    // 2. The new value (max or min, depending on the index)

    for(int i = 0; i < arr.length; i++) {
        if(i % 2 == 0) {
            // For even indices, place the maximum element.
            // Calculate the new value by adding the current element with (arr[maxIdx] % max) * max.
            // This way, the new value is stored in the most significant portion of the element.
            arr[i] = arr[i] + (arr[maxIdx] % max) * max;

            // Move the maxIdx pointer to the left.
            maxIdx--;
        } else {
            // For odd indices, place the minimum element.
            // Calculate the new value by adding the current element with (arr[minIdx] % max) * max.
            arr[i] = arr[i] + (arr[minIdx] % max) * max;

            // Move the minIdx pointer to the right.
            minIdx++;
        }
    }

    // Now, retrieve the new values from the elements.
    // Since we stored the new values in the most significant portion, we can retrieve them
    // by dividing each element by max.
    for(int i = 0; i < arr.length; i++) {
        arr[i] = arr[i] / max;
    }
}
```
### Explanation

- **Initial Setup:**
    
    - `maxIdx` is set to the last index, and `minIdx` is set to the first index. These indices will be used to track the largest and smallest elements, respectively.
    - `max` is chosen as a value slightly larger than the maximum element in the array, which ensures it can be used to store two values in a single array element.
- **First Loop (Storing Two Values in One Element):**
    
    - The loop iterates through the array.
    - For even indices, it places the largest available element at that position. It does so by using modulo and multiplication to encode this value alongside the original value.
    - For odd indices, it places the smallest available element.
    - The `maxIdx` and `minIdx` pointers are adjusted accordingly after each operation.
- **Second Loop (Extracting the New Values):**
    
    - The second loop divides each element by `max`, which effectively retrieves the new value (either the max or min) stored in each element.

### Result:

After the function executes, the array will be rearranged such that the first element is the largest, the second element is the smallest, the third is the second-largest, and so on.