---
created: 2024-08-07 20:28
tags:
  - "#framework"
Parent Topic:
  - "[[Java Frame Work.canvas|Java Frame Work]]"
Related Topics:
  - "[[Interface]]"
  - "[[Classes]]"
---
---
The entire java collection is built upon a set of standard interfaces, classes and algorithms.

- <mark style="background: #FFF3A3A6;">**Interfaces**</mark>: 
	- [[Set of JCF|Set]], List, Queue, Dequeue
- <mark style="background: #FFF3A3A6;">**Classes**</mark>: 
	- [[Array List]], [[Vector]],[[Linked List]],[[Priority Queue]],[[Set of JCF#HashSet|HashSet]],[[LinkedHashSet]],[[TreeSet]]
---
### Interfaces of collection:

![[Pasted image 20240807210442.png]]

### Collection Interface

- The Collection interface is the foundation upon which the collections framework is built because it must be implemented by any class that defines a collection.
- Collection is a [[Generic]] [[Interface]] that has this declaration:
```java
interface Collection<T>
```
Here, T specifies the type if objects that collection will hold.

---
### Interface List

- The Interface List extends **Collection** and declares the behavior of a collection that stores #sequenceOfElements. Elements can be inserted or accessed by their position in the list, using a zero-based index

- A List may contain #duplicate elements.

- List is a [[Generic]] interface that has this declaration:
```java
interface List<T>
```
Here, T specifies the type if objects that collection will hold.

---
##### Basic Methods Declared in List

![[Pasted image 20240807212630.png]]
![[Pasted image 20240807212803.png]]

---
#### Java Data Structures using Collection


| Data Structures    | List            | Queue              | Set               | Map               |
| ------------------ | --------------- | ------------------ | ----------------- | ----------------- |
| Indexed            | [[ArrayList]]   | [[Array Deque]]    | [[HashSet]]       | [[HashMap]]       |
| Sequential         | [[Linked List]] | [[Priority Queue]] | [[TreeSet]]       | [[TreeMap]]       |
| Indexed With Links |                 |                    | [[LinkedHashSet]] | [[LinkedHashMap]] |
| Bit String         |                 |                    | [[EnumSet]]       | [[EnumMap]]       |

