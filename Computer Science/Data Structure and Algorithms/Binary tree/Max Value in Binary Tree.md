---
created: 2024-08-05 23:54
tags:
  - traversal
  - review
  - "#recursion"
Parent Topic:
  - "[[Binary Tree]]"
  - "[[Recursion]]"
Related Topics:
  - "[[Level Order traversal]]"
sr-due: 2024-08-09
sr-interval: 3
sr-ease: 250
---
***
##### First thought:

Traverse through the tree and keep a variable max which will hold the max value.

```java
int findMax(treeNode root) {
	if(root == null) {
		return Integer.MIN_VALUE;
	}

	int result = root.data;
	int left = findMax(root.left);
	int right = findMax(root.right);

	if(left > result) {
		result = left;
	}
	if(right > result) {
		result = right;
	}

	return result;
}
```