
If you Want to find the nth node of the linked list from end, take two pointers pointing to head traverse one pointer n times
Now that you have traversed first pointer traverse both the pointers until you reach end, the second pointer now should be pointing to the desired node.
***
``` java
ListNode nthNodeFromEnd(int n) {  
    if (head == null) {  
        return null;  
    }  
  
    if(n <= 0) {  
        throw new IllegalArgumentException("Invalid argument");  
    }  
    ListNode refPtr = head;  
    ListNode mainPtr = head;  
    int count = 0;  
  
    while(count < n) {  
        if(refPtr == null) {  
            throw new IllegalArgumentException("The value exceeds the total number of nodes");  
        }  
        refPtr = refPtr.next;  
        count++;  
    }  
  
    while(refPtr != null) {  
        refPtr = refPtr.next;  
        mainPtr = mainPtr.next;  
    }  
  
    return mainPtr;  
}
```


***
Tags : [[Linked List]] #review 