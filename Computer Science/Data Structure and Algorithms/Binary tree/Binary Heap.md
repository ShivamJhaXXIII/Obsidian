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

- A Max Binary Heap is a complete binary tree in which each node value is >= than the values of its children. ^4585b1
- The maximum value is at the top which is root of complete binary tree. For its array representation its at index 1 i.e. heap[1];

#### Implementation of Max Binary Heap using priority Queue

![[Priority Queue#Max PriorityQueue]]

---
### Bottom-up Reheapify Max Heap / Swim

A Max heap is a complete binary tree in which each node value is>=than the values of its children.

After #inserting an element into heap. It may not satisfy above property. Thus, we use ==**Bottom up reheapify technique**== in which we adjust the locations of elements to satisfy the heap property.

![[Pasted image 20240810105635.png]]
In the above picture we can see after insertion of 10(which is greater than root node), the [[#^4585b1|condition]] is no more satisfied for Max heap.

Thus, when we have to insert the element in binary heap we apply bottom up reheapify.
```java
private void resize(int capacity) {  
        Integer[] temp = new Integer[capacity];  
  
        for(int i = 0; i < heap.length; i++) {  
            temp[i] = heap[i];  
        }  
        heap = temp;  
    }  
  
    public void insert(int data) {  
        if (n == heap.length - 1) {  
            resize(2* heap.length);  
        }  
        n++;  
        heap[n] = data;  
        swim(n);  
    }  
  
    public void swim(int k) {  
        while(k > 1 && heap[k] > heap[k/2]) { // checking whether the value is greater than its parents value  
            int temp = heap[k/2]; // Storing the value of the parent  
            heap[k/2] = heap[k];  
            heap[k] = temp;  
            k = k/2; // this allows to iterate through all the parents  
        }  
    }  
```
--- 
### Top Down Reheapify / Sink

After #deleting an element from heap. It may not satisfy heap properties. Thus, we perform top-down reheapify technique, in which we adjust the locations of elements to satisfy heap property.

This is the method to #delete the #MAX element of the binary heap.