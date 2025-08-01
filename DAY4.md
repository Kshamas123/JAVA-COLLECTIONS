SET
 
 1. What is Set in Java?
    
Set is a collection that does not allow duplicate elements.

It models the mathematical concept of a set.

Order is not guaranteed, except in some specific implementations.


Inheritance:

Set is an interface that extends the Collection interface.

Characteristics:

No duplicate elements allowed.

At most one null element (depends on implementation, e.g., HashSet allows one).

Unordered: Set does not maintain insertion order (except LinkedHashSet which does).

Common Implementations:

HashSet (uses a hash table, no ordering guaranteed)

LinkedHashSet (insertion order maintained)

TreeSet (sorted order, no null allowed)

HashSet in Java (java.util.HashSet)

1. Definition
   
HashSet is a class that implements the Set interface.

It uses a hash table for storage.

No duplicate elements allowed.

Null is allowed (only one null value).

Insertion order is not preserved.

HashSet is backed by a HashMap. When you add an element to the HashSet, it is internally added to the HashMap as a key with a dummy value (e.g., PRESENT).


HASHSET IS NOT  THREAD SAFE (ITS NOT SYNCHRONIZED)   

