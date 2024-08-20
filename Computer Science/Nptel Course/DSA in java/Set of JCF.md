---
created: 2024-08-09 19:41
tags:
  - "#continue"
Parent Topic: 
Related Topics:
---
***
# from 12 minutes of lecture 8

**Set** is a type of [[Collections in JCF |Collection]] which does not hold any duplicate elements. That means an element can only exist once in a set. 

Unlike other [[Collections in JCF |Collection]] type such as [[Arrays]], [[List]], [[Linked List]], Set collection has distinctive characteristics-
1. It does not hold any duplicate elements.
2. Elements are not stored in order. That means you cannot expect elements sorted in any order when iterating over elements of **Set**.
***
#### Collections of JCF

Following are the [[Interface]] and [[Classes]] for managing Set objects in java

- **Interface** - [[Set of JCF|Set]], [[#SortedSet]], [[#NavigableSet]]
- Classes - [[EnumSet]], [[#HashSet]], [[LinkedHashSet]], [[TreeSet]]
***
#### Interface Set

Set is a [[Generic]] interface that has this declaration:
```java
interface Set<T>
```
Here, T Specifies the type of objects which the Set will hold.
***
#### Methods Defined for a Set

|Method|Description|
|---|---|
|[add(element)](https://www.geeksforgeeks.org/set-add-method-in-java-with-examples/)|This method is used to add a specific element to the set. The function adds the element only if the specified element is not already present in the set else the function returns False if the element is already present in the Set.|
|[addAll(collection)](https://www.geeksforgeeks.org/set-addall-method-in-java-with-examples/)|This method is used to append all of the elements from the mentioned collection to the existing set. The elements are added randomly without following any specific order.|
|[clear()](https://www.geeksforgeeks.org/set-clear-method-in-java-with-examples/)|This method is used to remove all the elements from the set but not delete the set. The reference for the set still exists.|
|[contains(element)](https://www.geeksforgeeks.org/set-contains-method-in-java-with-examples/)|This method is used to check whether a specific element is present in the Set or not.|
|[containsAll(collection)](https://www.geeksforgeeks.org/set-containsall-method-in-java-with-examples/)|This method is used to check whether the set contains all the elements present in the given collection or not. This method returns true if the set contains all the elements and returns false if any of the elements are missing.|
|[hashCode()](https://www.geeksforgeeks.org/set-hashcode-method-in-java-with-examples/)|This method is used to get the hashCode value for this instance of the Set. It returns an integer value which is the hashCode value for this instance of the Set.|
|isEmpty()|This method is used to check whether the set is empty or not.|
|[iterator()](https://www.geeksforgeeks.org/set-iterator-method-in-java-with-examples/)|This method is used to return the [iterator](https://www.geeksforgeeks.org/iterators-in-java/) of the set. The elements from the set are returned in a random order.|
|[remove(element)](https://www.geeksforgeeks.org/set-remove-method-in-java-with-examples/)|This method is used to remove the given element from the set. This method returns True if the specified element is present in the Set otherwise it returns False.|
|[removeAll(collection)](https://www.geeksforgeeks.org/set-removeall-method-in-java-with-examples/)|This method is used to remove all the elements from the collection which are present in the set. This method returns true if this set changed as a result of the call.|
|[retainAll(collection)](https://www.geeksforgeeks.org/set-retainall-method-in-java-with-example/)|This method is used to retain all the elements from the set which are mentioned in the given collection. This method returns true if this set changed as a result of the call.|
|[size()](https://www.geeksforgeeks.org/set-size-method-in-java-with-example/)|This method is used to get the size of the set. This returns an integer value which signifies the number of elements.|
|[toArray()](https://www.geeksforgeeks.org/set-toarray-method-in-java-with-example/)|This method is used to form an array of the same elements as that of the Set.|

***
#### SortedSet

The Sorted Set as the name suggest, the elements are organized in sorted manner.

<mark style="background: #FFB8EBA6;">The SortedSet interface extends Set and declares the behavior of a set sorted in ascending order.</mark>

SortedSet is a [[Generic]] interface that has this declaration:
```java
interface SortedSet<T>
```
Here, T Specifies the type of objects which the Set will hold.

***
#### Methods Exclusive for SortedSet

| Methods                                                                                              | Description                                                                                                                                                       |
| ---------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [****comparator()****](https://www.geeksforgeeks.org/treeset-comparator-method-in-java/)             | This method returns the comparator used to order the elements in this set, or null if this set uses the natural ordering of its elements.                         |
| [****first()****](https://www.geeksforgeeks.org/sortedset-first-method-in-java/)                     | This method returns the first(lowest) element present in this set.                                                                                                |
| [****hashCode()****](https://www.geeksforgeeks.org/sortedset-hashcode-method-in-java-with-examples/) | This method is used to get the hashCode value for this instance of the Set. It returns an integer value which is the hashCode value for this instance of the Set. |
| [****headSet(element)****](https://www.geeksforgeeks.org/sortedset-headset-method-in-java/)          | This method returns the elements which are less than the element that are present in the sorted set.                                                              |
| [****last()****](https://www.geeksforgeeks.org/sortedset-last-method-in-java/)                       | This method returns the last(highest) element present in the set.                                                                                                 |
| [****subSet(element1, element2)****](https://www.geeksforgeeks.org/sortedset-subset-method-in-java/) | This method returns a sorted subset from the set containing the elements between element1 and element2.                                                           |
| [****tailSet(element)****](https://www.geeksforgeeks.org/sortedset-tailset-method-in-java/)          | This method returns the elements which are greater than or equal to the element that are present in the sorted set.                                               |
***
#### NavigableSet

NavigableSet represents a navigable set in [[Java Frame Work.canvas|Java Frame Work]] . The NavigableSet interface inherits from the [[#SortedSet]]. It behaves like a SortedSet with the exception that we have navigation methods available in addition to the sorting mechanisms of the SortedSet.

**Declaration:** The NavigableSet is declared as

```java
public interface NavigableSet<E>  extends SortedSet<E>
```

##### **Creating NavigableSet Objects**

Since NavigableSet is an interface, [[Objects]] cannot be created of the type NavigableSet. We always need a class that extends this list in order to create an object. And also, after the introduction of Generics in Java 1.5, it is possible to restrict the type of object that can be stored in the NavigableSet. This type-safe set can be defined as:

```java
NavigableSet<Obj> set = new TreeSet<Obj> ();
```
---
### Methods of Navigable Set

The following are the methods present in the NavigableSet interface. 

|METHOD|DESCRIPTION|
|---|---|
|[ceiling?(E e)](https://www.geeksforgeeks.org/navigableset-ceiling-method-in-java/)|Returns the least element in this set greater than or equal to the given element, or null if there is no such element.|
|[descendingIterator()](https://www.geeksforgeeks.org/navigableset-descendingiterator-method-in-java/)|Returns an iterator over the elements in this set, in descending order.|
|[descendingSet()](https://www.geeksforgeeks.org/navigableset-descendingset-method-in-java/)|Returns a reverse order view of the elements contained in this set.|
|[floor?(E e)](https://www.geeksforgeeks.org/navigableset-floor-method-in-java/)|Returns the greatest element in this set less than or equal to the given element, or null if there is no such element.|
|[headSet?(E toElement)](https://www.geeksforgeeks.org/navigableset-headset-method-in-java/)|Returns a view of the portion of this set whose elements are strictly less than toElement.|
|[headSet?(E toElement, boolean inclusive)](https://www.geeksforgeeks.org/navigableset-java-examples/headSet?(E%20toElement,%20boolean%20inclusive))|Returns a view of the portion of this set whose elements are less than (or equal to, if inclusive is true) toElement.|
|[higher?(E e)](https://www.geeksforgeeks.org/navigableset-higher-method-in-java/)|Returns the least element in this set strictly greater than the given element, or null if there is no such element.|
|[iterator()](https://www.geeksforgeeks.org/navigableset-iterator-method-in-java/)|Returns an iterator over the elements in this set, in ascending order.|
|[lower?(E e)](https://www.geeksforgeeks.org/navigableset-lower-method-in-java/)|Returns the greatest element in this set strictly less than the given element, or null if there is no such element.|
|[pollFirst()](https://www.geeksforgeeks.org/navigableset-pollfirst-method-in-java/)|Retrieves and removes the first (lowest) element, or returns null if this set is empty.|
|[pollLast()](https://www.geeksforgeeks.org/navigableset-polllast-method-in-java/)|Retrieves and removes the last (highest) element, or returns null if this set is empty.|
|[subSet?(E fromElement, boolean](https://www.geeksforgeeks.org/navigableset-subset-method-in-java/)<br><br>[fromInclusive, E toElement, boolean toInclusive)](https://www.geeksforgeeks.org/navigableset-subset-method-in-java/)|Returns a view of the portion of this set whose elements range from fromElement to toElement.|
|[subSet?(E fromElement, E toElement)](https://www.geeksforgeeks.org/navigableset-subset-method-in-java/)|Returns a view of the portion of this set whose elements range from fromElement, inclusive, to toElement, exclusive.|
|tailSet?(E fromElement)|Returns a view of the portion of this set whose elements are greater than or equal to fromElement.|
|tailSet?(E fromElement, boolean inclusive)|Returns a view of the portion of this set whose elements are greater than (or equal to, if inclusive is true) fromElement.|

---
#### HashSet

Java HashSet class implements the Set interface, backed by hash table which is actually a [[HashMap]].

##### Java HashSet Features

A few important features of HashSet are mentioned below:

- Implements [Set Interface](https://www.geeksforgeeks.org/set-in-java/).
- The underlying data structure for HashSet is ==[Hashtable](https://www.geeksforgeeks.org/hashtable-in-java/).
- As it implements the Set Interface, ==duplicate values are not allowed==.
- Objects that you insert in HashSet are not guaranteed to be inserted in the same order. Objects are inserted based on their hash code.
- NULL elements are allowed in HashSet.
- HashSet also implements ****Serializable**** and ****Cloneable**** interfaces.

Syntax:
```java
Set<E> VariableName - new HashSet<>();
```

---
### Methods in HashSet

|Method|Description|
|---|---|
|[add(E e)](https://www.geeksforgeeks.org/hashset-add-method-in-java/)|Used to add the specified element if it is not present, if it is present then return false.|
|[clear()](https://www.geeksforgeeks.org/hashset-clear-method-in-java/)|Used to remove all the elements from the set.|
|[contains(Object o)](https://www.geeksforgeeks.org/hashset-contains-method-in-java/)|Used to return true if an element is present in a set.|
|[remove(Object o)](https://www.geeksforgeeks.org/hashset-remove-method-in-java/)|Used to remove the element if it is present in set.|
|[iterator()](https://www.geeksforgeeks.org/hashset-iterator-method-in-java/)|Used to return an iterator over the element in the set.|
|[isEmpty()](https://www.geeksforgeeks.org/hashset-isempty-method-in-java/)|Used to check whether the set is empty or not. Returns true for empty and false for a non-empty condition for set.|
|[size()](https://www.geeksforgeeks.org/hashset-size-method-in-java/)|Used to return the size of the set.|
|[clone()](https://www.geeksforgeeks.org/hashset-clone-method-in-java/)|Used to create a shallow copy of the set.|

---
