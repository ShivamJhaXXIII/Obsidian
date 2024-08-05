---
created: 2024-08-04 14:11
tags:
  - traversal
  - review
Parent Topic:
  - "[[Binary Tree]]"
Related Topics:
  - "[[Post Order Traversal]]"
  - "[[Pre Order Traversal]]"
  - "[[In order traversal]]"
---

***
**Level Order Traversal** technique is defined as a method to traverse a Tree such that all nodes present in the same level are traversed completely before traversing the next level.

```java
void levelOrder(treeNode root) {  
    if(root == null) {  
        return;  
    }  
    Queue<treeNode> queue = new LinkedList<>();  
    queue.offer(root);  
  
    while(!queue.isEmpty()) {  
        treeNode temp = queue.poll();  
  
        System.out.print(temp.data + " ");  
        if(temp.left != null) {  
            queue.offer(temp.left);  
        }  
        if(temp.right != null) {  
            queue.offer(temp.right);  
        }  
    }  
}
```