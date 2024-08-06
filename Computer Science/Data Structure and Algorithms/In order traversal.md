---
created: 2024-08-03 16:43
tags:
  - traversal
Parent Topic:
  - "[[Binary Tree]]"
Related Topics:
  - "[[Pre Order Traversal]]"
  - "[[Post Order Traversal]]"
---

***

#flashcards
In Order traversal:: left - center - right
<!--SR:!2024-08-10,4,270-->
In this traversal we first print the leftmost node then its corresponding middle node then right node.


<!--SR:!2024-08-08,4,270-->
#### Non - recursive method
###### Approach 
``` java
void inOrder(treeNode root) {  
    if(root == null) {  
        return;  
    }
  
    Stack<treeNode> stack = new Stack<>();  
  
  
    treeNode temp = root;  
  
    while(temp != null || !stack.isEmpty()) {  
        if(temp != null) {  
            stack.push(temp);  
            temp = temp.left;  
        } else {  
            temp = stack.pop();  
            System.out.print(temp.data + " ");  
            temp = temp.right;  
        }  
    }  
}
```

Recursive Method
```java
void inOrder(treeNode root) {  
    if(root == null) {  
        return;  
    }  
  
    inOrder(root.left);  
    System.out.print(root.data + " ");  
    inOrder(root.right);  
}
```



