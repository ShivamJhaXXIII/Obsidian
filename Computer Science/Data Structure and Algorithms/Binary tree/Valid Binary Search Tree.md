---
created: 2024-08-06 22:06
tags:
  - "#BinaryTree"
  - review
Parent Topic:
  - "[[Binary Search Tree]]"
Related Topics:
---
***
==**Problem statement : Given the root of a binary tree, determine if it is a valid Binary search tree or not.**==
###### A valid BST is define as follows : 

- The left subtree of a node contains only nodes with keys less than the node’s key.
- The right subtree of a node contains only nodes with keys greater than the node’s key.
- Both the left and right subtrees must also be binary search trees.
- Each node (item in the tree) has a distinct key.

```java
public boolean validBst(treeNode root, long min, long max) {  
    if(root == null) {  
        return true;  
    }  
  
    if(root.data <= min || root.data >= max) {  
        return false;  
    }  
    boolean left = validBst(root.left, min, root.data);  
  
    if (left) {  
        boolean right = validBst(root.right, root.data, max);  
        return right;  
    }  
    return false;  
}
```



