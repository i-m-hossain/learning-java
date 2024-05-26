# Java Collection Framework
<!-- TOC -->
* [Java Collection Framework](#java-collection-framework)
  * [What is java collection framework?](#what-is-java-collection-framework)
  * [Why we need java collection framework?](#why-we-need-java-collection-framework)
  * [Collection:](#collection)
* [Java Collection Methods and Usage](#java-collection-methods-and-usage)
  * [Diagram](#diagram)
<!-- TOC -->
## What is java collection framework?
- Collection is nothing but a group of Objects
- Present in java.util package
- Framework provide us the architecture to manage these "group of objects" i.e. add, update, delete, search etc.

## Why we need java collection framework?
- Prior to JCF, we have Array, Vector, Hash Tables
- But problem with that is, there is no  common interface, so its difficult to remember the methods for each.

```java
import java.util.ArrayList;
import java.util.List;

List<Integer> numbers = new ArrayList<>();

```

## Collection:
It represents the group of object. Its an interface which provides methods to work on group of objects. The most common used methods are below
# Java Collection Methods and Usage

| Collection Class | Method                              | Description                                                             | Usage Example                                                   |
|------------------|-------------------------------------|-------------------------------------------------------------------------|-----------------------------------------------------------------|
| **ArrayList**    | `add(E e)`                          | Appends the specified element to the end of this list.                  | Adding an item to a shopping cart                               |
|                  | `remove(int index)`                 | Removes the element at the specified position in this list.             | Removing an item from a list by its position                    |
|                  | `isEmpty()`                         | Returns true if this list contains no elements.                         | Checking if the list is empty                                   |
|                  | `size()`                            | Returns the number of elements in this list.                            | Checking the number of items in a list                          |
|                  | `contains(Object o)`                | Returns true if this list contains the specified element.               | Checking if a list contains a specific item                     |
|                  | `toArray()`                         | Returns an array containing all of the elements in this list.           | Converting the list to an array                                 |
|                  | `addAll(Collection<? extends E> c)` | Appends all of the elements in the specified collection to the end of this list. | Merging another list into this list            |
|                  | `removeAll(Collection<?> c)`        | Removes from this list all of its elements that are contained in the specified collection. | Removing specific items from the list      |
|                  | `stream()`                          | Returns a sequential Stream with this collection as its source.         | Processing the list with stream operations                      |
|                  | `parallelStream()`                  | Returns a parallel Stream with this collection as its source.           | Processing the list with parallel stream operations              |
|                  | `iterator()`                        | Returns an iterator over the elements in this list in proper sequence.  | Iterating over the elements of the list                          |
| **LinkedList**   | `add(E e)`                          | Appends the specified element to the end of this list.                  | Adding an item to a collection                                  |
|                  | `remove(int index)`                 | Removes the element at the specified position in this list.             | Removing an item from a list by its position                    |
|                  | `isEmpty()`                         | Returns true if this list contains no elements.                         | Checking if the list is empty                                   |
|                  | `size()`                            | Returns the number of elements in this list.                            | Checking the number of items in a list                          |
|                  | `contains(Object o)`                | Returns true if this list contains the specified element.               | Checking if a list contains a specific item                     |
|                  | `toArray()`                         | Returns an array containing all of the elements in this list.           | Converting the list to an array                                 |
|                  | `addAll(Collection<? extends E> c)` | Appends all of the elements in the specified collection to the end of this list. | Merging another list into this list            |
|                  | `removeAll(Collection<?> c)`        | Removes from this list all of its elements that are contained in the specified collection. | Removing specific items from the list      |
|                  | `stream()`                          | Returns a sequential Stream with this collection as its source.         | Processing the list with stream operations                      |
|                  | `parallelStream()`                  | Returns a parallel Stream with this collection as its source.           | Processing the list with parallel stream operations              |
|                  | `iterator()`                        | Returns an iterator over the elements in this list in proper sequence.  | Iterating over the elements of the list                          |
| **Stack**        | `add(E e)`           | Pushes an element onto the stack represented by this list.              | Adding an item to a stack                                        |
|                  | `remove(int index)`  | Removes the element at the specified position in this stack.            | Removing an item from a stack                                    |
|                  | `isEmpty()`          | Tests if this stack is empty.                                           | Checking if there are any items in the stack                     |
|                  | `size()`             | Returns the number of elements in this stack.                           | Checking the number of items in the stack                        |
|                  | `contains(Object o)` | Returns true if this stack contains the specified element.              | Checking if the stack contains a specific item                   |
|                  | `toArray()`          | Returns an array containing all of the elements in this stack.          | Converting the stack to an array                                 |
|                  | `addAll(Collection<? extends E> c)` | Pushes all of the elements in the specified collection onto the stack. | Adding multiple items to the stack                               |
|                  | `removeAll(Collection<?> c)` | Removes from this stack all of its elements that are contained in the specified collection. | Removing specific items from the stack      |
|                  | `stream()`           | Returns a sequential Stream with this stack as its source.              | Processing the stack with stream operations                      |
|                  | `parallelStream()`   | Returns a parallel Stream with this stack as its source.                | Processing the stack with parallel stream operations              |
|                  | `iterator()`         | Returns an iterator over the elements in this stack in proper sequence. | Iterating over the elements of the stack                         |
| **Queue**        | `add(E e)`           | Inserts the specified element into this queue.                          | Adding a task to a task queue                                    |
|                  | `remove()`           | Retrieves and removes the head of this queue.                           | Processing and removing a task from the queue                    |
|                  | `isEmpty()`          | Returns true if this queue contains no elements.                        | Checking if the queue is empty                                   |
|                  | `size()`             | Returns the number of elements in this queue.                           | Checking the number of tasks in the queue                        |
|                  | `contains(Object o)` | Returns true if this queue contains the specified element.              | Checking if the queue contains a specific task                   |
|                  | `toArray()`          | Returns an array containing all of the elements in this queue.          | Converting the queue to an array                                 |
|                  | `addAll(Collection<? extends E> c)` | Inserts all of the elements in the specified collection into this queue. | Adding multiple tasks to the queue                            |
|                  | `removeAll(Collection<?> c)` | Removes from this queue all of its elements that are contained in the specified collection. | Removing specific tasks from the queue  |
|                  | `stream()`           | Returns a sequential Stream with this queue as its source.              | Processing the queue with stream operations                      |
|                  | `parallelStream()`   | Returns a parallel Stream with this queue as its source.                | Processing the queue with parallel stream operations              |
|                  | `iterator()`         | Returns an iterator over the elements in this queue in proper sequence. | Iterating over the tasks in the queue                            |
| **HashMap**      | `put(K key, V value)` | Associates the specified value with the specified key in this map.     | Storing user information with user ID as key                    |
|                  | `remove(Object key)`  | Removes the mapping for the specified key from this map if present.    | Deleting a user from the map                                     |
|                  | `isEmpty()`          | Returns true if this map contains no key-value mappings.               | Checking if the map is empty                                     |
|                  | `size()`             | Returns the number of key-value mappings in this map.                  | Checking the number of entries in the map                        |
|                  | `containsKey(Object key)` | Returns true if this map contains a mapping for the specified key.   | Checking if a user ID exists in the map                          |
|                  | `containsValue(Object value)` | Returns true if this map maps one or more keys to the specified value. | Checking if a value exists in the map                       |
|                  | `toArray()`          | Returns an array containing all of the key-value mappings in this map. | Converting the map to an array of entries                        |
|                  | `addAll(Map<? extends K, ? extends V> m)` | Copies all of the mappings from the specified map to this map. | Merging another map into this map                              |
|                  | `removeAll(Collection<?> c)` | Removes from this map all of its mappings that are contained in the specified collection. | Removing specific entries from the map      |
|                  | `stream()`           | Returns a sequential Stream with the mappings in this map as its source. | Processing the map with stream operations                      |
|                  | `parallelStream()`   | Returns a parallel Stream with the mappings in this map as its source.  | Processing the map with parallel stream operations              |
|                  | `keySet()`           | Returns a Set view of the keys contained in this map.                   | Getting a set of all user IDs                                    |
|                  | `values()`           | Returns a Collection view of the values contained in this map.          | Getting a collection of all values in the map                    |
|                  | `entrySet()`         | Returns a Set view of the mappings contained in this map.               | Getting a set of all key-value pairs                             |

## Diagram
![img_3.png](images/img_3.png)