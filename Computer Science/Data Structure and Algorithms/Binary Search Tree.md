---
created: 2024-08-06 09:19
tags:
  - review
  - flashcards
Parent Topic: 
Related Topics:
---

***
#### What is a Binary Search Tree?

It is a type of binary tree in which the data is organized in a ordered manner which makes it faster to search, insert or delete desired data.

***

###### <u>Representation of Binary Search tree</u>

![[Pasted image 20240806092752.png]]

##### <u>Properties of Binary Search Tree</u> 

- The left subtree of the node consists of the values lesser than that of parent node.
- The Right subtree consists of value greater than that of parent node.

---

##### <span style = "color:blue"><u>Structure of Binary Search tree</u></span>

The Structure of Binary Search tree is same as the [[Binary Tree]] structure.

Each Binary search tree node has:: three parts:

1. Data
2. Pointer to the Left Node
3. Pointer to the Right Node
<!--SR:!2024-08-09,3,250-->

```java
public class TreeNode {
	private int data;
	private TreeNode left;
	private TreeNode right;

	public TreeNode(int data) {
		this.data = data;
		this.left = null;
		this.right = null;
	}
}
```

***

##### <span style = "color:cyan"><u>Insertion In Binary Search Tree</u></span>

###### Recursive way : 

```java
public treeNode insert(treeNode root, int value) {  
    if(root == null) {  
        root = new treeNode(value);  
    }  
  
    if(value < root.data) {  
        root.left = insert(root.left, value);  
    }  
  
    if(value > root.data) {  
        root.right = insert(root.right, value);  
    }  
    return root;  
}
```


