---
created: 2024-08-07 14:14
tags:
  - Arrays
  - matrices
  - traversal
  - review
  - twoPointers
Parent Topic:
  - "[[Arrays]]"
Related Topics:
---
***
Problem Statement :
![[Pasted image 20240807141536.png]]

```java
void spiralPrint(int[][] matrix, int r, int c) {
    int i, k = 0, l = 0;

    // k - starting row index
    // l - starting column index
    // r - ending row index
    // c - ending column index
    
    // Loop until we traverse the entire matrix
    while (k < r && l < c) {
        
        // Print the first row from the remaining rows
        for (i = l; i < c; i++) {
            System.out.print(matrix[k][i] + " ");
        }
        k++; // Move down to the next row
        
        // Print the last column from the remaining columns
        for (i = k; i < r; i++) {
            System.out.print(matrix[i][c - 1] + " ");
        }
        c--; // Move left to the previous column
        
        // Print the last row from the remaining rows, if any
        if (k < r) {
            for (i = c - 1; i >= l; i--) {
                System.out.print(matrix[r - 1][i] + " ");
            }
            r--; // Move up to the previous row
        }
        
        // Print the first column from the remaining columns, if any
        if (l < c) {
            for (i = r - 1; i >= k; i--) {
                System.out.print(matrix[i][l] + " ");
            }
            l++; // Move right to the next column
        }
    }
}
```

![[Pasted image 20240807165643.png]]

---
### Using vectors

There are several ways to print a matrix in a spiral order. Another approach is to use direction vectors to handle the movement in the matrix. This approach is more systematic and can be easier to understand and modify.

Here's an alternative implementation using direction vectors:
```java
void spiralPrint(int[][] matrix, int r, int c) {
    // Define direction vectors for right, down, left, and up
    int[] dirRow = {0, 1, 0, -1};
    int[] dirCol = {1, 0, -1, 0};
    
    // Initialize boundaries for the matrix
    int top = 0, bottom = r - 1, left = 0, right = c - 1;
    
    // Initialize starting point
    int row = 0, col = 0;
    
    // Start with direction index 0 (right)
    int dirIndex = 0;
    
    // Iterate until we print all elements in the matrix
    for (int i = 0; i < r * c; i++) {
        // Print the current element
        System.out.print(matrix[row][col] + " ");
        
        // Calculate the next position
        int nextRow = row + dirRow[dirIndex];
        int nextCol = col + dirCol[dirIndex];
        
        // Check if the next position is out of the current boundary
        if (nextRow > bottom || nextRow < top || nextCol > right || nextCol < left) {
            // Change direction (right -> down -> left -> up)
            dirIndex = (dirIndex + 1) % 4;
            
            // Update boundaries based on the new direction
            if (dirIndex == 0) { // Right
                top++;
            } else if (dirIndex == 1) { // Down
                right--;
            } else if (dirIndex == 2) { // Left
                bottom--;
            } else if (dirIndex == 3) { // Up
                left++;
            }
        }
        
        // Update position based on the new direction
        row += dirRow[dirIndex];
        col += dirCol[dirIndex];
    }
}

```

### Explanation:

1. **Direction Vectors:**
    
    - `dirRow` and `dirCol` arrays represent the change in row and column indices for each direction: right, down, left, and up.
    - `dirRow = {0, 1, 0, -1}` and `dirCol = {1, 0, -1, 0}` correspond to right, down, left, and up respectively.
2. **Boundaries:**
    
    - `top`, `bottom`, `left`, and `right` represent the current boundaries of the matrix that we need to print.
3. **Starting Point:**
    
    - Start at the top-left corner of the matrix with `row = 0` and `col = 0`.
4. **Direction Index:**
    
    - `dirIndex` keeps track of the current direction (0: right, 1: down, 2: left, 3: up).
5. **Iterate through the matrix:**
    
    - Loop until we print all elements in the matrix.
    - Print the current element at `matrix[row][col]`.
    - Calculate the next position based on the current direction.
    - If the next position is out of the current boundary, update the direction and adjust the boundaries accordingly.
    - Update the current position based on the new direction.

This approach uses direction vectors to systematically handle the movement through the matrix, making the code easier to follow and extend.