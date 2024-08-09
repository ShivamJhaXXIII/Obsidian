---
created: 2024-08-08 22:34
tags: 
Parent Topic: 
Related Topics:
---
***
The **Binary heap** is a data structure that helps us in implementing [[Priority Queue]] operations efficiently. A binary heap is a complete binary tree in which each node value is either >= or <= the values of its children.
- In the min heap the parent node has lesser value than child nodes.
- In the max heap the parent node has greater value than child nodes.
![[Pasted image 20240808223838.png]]

The Binary Heap is a [[Complete Binary Tree]].

---

### Representation of Binary Heaps

- Binary Heaps are usually implemented using arrays.
- The first entry of array is taken as empty.
- As Binary heaps are complete binary tree level by level from left to right.

![[Pasted image 20240808235730.png]]

---
### Parent-child calculations in Binary heaps

Child of a parent node is given by:

$$
2*k,2*k+1
$$
Here, k is the index of the parent node

![[Pasted image 20240809000140.png]]
Parent index is given by: $$ k/2$$
![[Pasted image 20240809001311.png]]

---
### Max Binary Heap

- A Max Binary Heap is a complete binary tree in which each node value is >= than the values of its children.
- The maximum value is at the top which is root of complete binary tree. For its array representation its at index 1 i.e. heap[1];



 
