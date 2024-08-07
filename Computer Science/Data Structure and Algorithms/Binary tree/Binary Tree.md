Binary Tree is a non - linear data structure where each node has at most two child nodes.

The Topmost node of the binary tree is called **Root**

### Representation of Binary trees

Each binary tree node has three parts: 
1. Data
2. Pointer to the Left Node
3. Pointer to the Right Node

![[Representation-of-Binary-Tree.webp]]  

``` java
private treeNode root;  
  
private static class treeNode {  
    private final int data;  
    private treeNode left;  
    private treeNode right;  
  
  
    public treeNode(int data) {  
        this.data = data;  
        this.left = null;  
        this.right = null;  
    }  
}
```
---


### Types of Binary trees
Binary trees can be classified into multiple types based on multiple factors :
-  ****On the basis of Number of Children****
    - [Full Binary Tree](https://www.geeksforgeeks.org/full-binary-tree/)
    - [Degenerate Binary Tree](https://www.geeksforgeeks.org/introduction-to-degenerate-binary-tree/)
    - [Skewed Binary Trees](https://www.geeksforgeeks.org/skewed-binary-tree/)
-  ****On the basis of Completion of Levels****
    - [Complete Binary Tree](https://www.geeksforgeeks.org/complete-binary-tree/)
    - [Perfect Binary Tree](https://www.geeksforgeeks.org/perfect-binary-tree/)
    - [Balanced Binary Tree](https://www.geeksforgeeks.org/balanced-binary-tree/)
- ****On the basis of Node Values:****
    - [Binary Search Tree](https://www.geeksforgeeks.org/binary-search-tree-data-structure/)
    - [AVL Tree](https://www.geeksforgeeks.org/introduction-to-avl-tree/)
    - [Red Black Tree](https://www.geeksforgeeks.org/introduction-to-red-black-tree/)
    - [B Tree](https://www.geeksforgeeks.org/introduction-of-b-tree-2/)
    - [B+ Tree](https://www.geeksforgeeks.org/introduction-of-b-tree/)
    - [Segment Tree](https://www.geeksforgeeks.org/segment-tree-data-structure/)



Important related topics:
[[Linked List]]
[[In order traversal|In order Traversal]]
[[Pre Order Traversal]]
[[Post Order Traversal]]


