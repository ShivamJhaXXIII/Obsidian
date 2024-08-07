To find the middle node of the linked list take a pointer named #fastPtr and a #slowPtr.
Next traverse the fastPtr to skip one node each time and the slowPtr does not skip any, once the fastPtr reaches end the slowPtr points to middle node.

Imagine someone running twice the speed of you, by the time he reaches the finish line you will be only halfway through the race.
***
``` java
ListNode middleOfSLL() {  
    if(head == null) {  
        return null;  
    }  
    ListNode fastPtr = head;  
    ListNode slowPtr = head;  
  
  
    while(fastPtr != null && fastPtr.next != null) {  
        slowPtr = slowPtr.next;  
        fastPtr = fastPtr.next.next;  
    }  
    return slowPtr;  
}
```

Related Topics:
[[Linked List]]
[[nth node from end]] 