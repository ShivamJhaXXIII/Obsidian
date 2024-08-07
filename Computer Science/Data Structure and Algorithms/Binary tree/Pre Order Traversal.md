Parent Topic : [[Binary Tree]] #traversal 

In Pre order Traversal first we print the parent node than its left child node then at last right node.
***
Recursive Method

```java
void preOrder(treeNode root) {
	if(root == null) {
		return;
	}
	System.out.print(root.data + " ");
	preOrder(root.left);
	preOrder(root.right);
}
```

Non - Recursive Method

```java
void preOrder(treeNode root) {
	if(root == null) {
		return;
	}
	Stack<treeNode> stack = new Stack();
	stack.push(root);

	while(!stack.isEmpty()) {
		treeNode temp = stack.pop();
		System.out.print(temp.data + " ");
		if(temp.right != null) {
			stack.push(temp.right);
		}
		if(temp.left != null) {
			stack.push(temp.left);
		}
	}
}
```


