---
created: 2024-08-08 22:28
tags: 
Parent Topic: 
Related Topics:
---
***
**Priority Queue** are special Queue that allows us to find minimum/maximum element among collection of elements in constant time. It supports following operations -
- insert(key) - Insert a key into the priority queue.
- deleteMax()/deleteMin() - return and remove largest/smallest key.
- getMax()/getMin() - return largest/smallest key.

---
### Max PriorityQueue

```java
public class MaxPQ {  
    private Integer[] heap;  
    private int n; // Size of the max heap  
    public MaxPQ(int capacity) {  
        heap = new Integer[capacity + 1];  
        n = 0;  
    }  
  
    public boolean isEmpty() {  
        return n==0;  
    }  
  
    public int size() {  
        return n;  
    }  
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
    public static void main(String[] args) {  
        MaxPQ pq = new MaxPQ(3);  
        System.out.println(pq.size());  
        System.out.println(pq.isEmpty());  
        pq.insert(5);  
  
    }  
  
}
```
