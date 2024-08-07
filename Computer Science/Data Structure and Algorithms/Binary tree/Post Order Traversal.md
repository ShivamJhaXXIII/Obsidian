Parent Topic : [[Binary Tree ]] #traversal 

In this traversal the left subtree is visited than right subtree than the central node.
***
Recursive Method
```java
void postOrder(treeNode root) {  
    if(root == null) {  
        return;  
    }  
    postOrder(root.left);  
    postOrder(root.right);  
    System.out.print(root.data+ " ");  
}
```
Non - Recursive method

```java
void postOrder(treeNode root) {  
    if(root == null) {  
        return;  
    }  
    Stack<treeNode> stack = new Stack<>();  
    treeNode current = root;  
    while(!stack.isEmpty() || current != null) {  
        if(current != null) {  
            stack.push(current);  
            current = current.left;  
        } else {  
            treeNode temp = stack.peek().right;  
            if(temp == null) {  
                temp = stack.pop();  
                System.out.print(temp.data + " ");  
                while(!stack.isEmpty() && temp == stack.peek().right) {  
                    temp = stack.pop();  
                    System.out.print(temp.data+ " ");  
                }  
            } else {  
                current = temp;  
            }  
        }  
    }  
}
```

Related Topics :

[[Pre Order Traversal]]
[[In order traversal]]
