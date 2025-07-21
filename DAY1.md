The Java Collections Framework (JCF) is a unified architecture for representing and manipulating collections of objects. It consists of:
1. Interfaces
These define the blueprint (structure) of data structures — what operations are allowed, without providing the exact code for how.
Collection is the root interface of the framework.
Other important interfaces:
List, Set, Queue → these extend Collection

Map → a separate interface (does not extend Collection)


3. Concrete Classes
These are the actual implementations of the interfaces. They define how the data structure behaves internally.
Interface	Implementing Classes
List	ArrayList, LinkedList, Vector, Stack
Set	HashSet, TreeSet, LinkedHashSet
Queue	PriorityQueue, ArrayDeque
Map	HashMap, TreeMap, LinkedHashMap, Hashtable

📌 Classes implement interfaces to provide actual working data structures


3. Algorithms
These are utility methods (like sort(), reverse(), shuffle(), min(), max()) provided by the Collections class — a final class with static methods to operate on collections.
Provided by: java.util.Collections
Works on any class implementing Collection or Map

📌 Collections (with an "s") is a helper class, not an interface.
