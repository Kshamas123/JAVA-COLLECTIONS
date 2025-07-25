1. List Interface Overview
Part of the Java Collection Framework (java.util package).
Extends the Collection interface.
Maintains insertion order.
Allows duplicate elements.
Provides indexed access (via get(int index)).

🔹 3. Internal Working (Simple Explanation)
✅ ArrayList
Stores elements in a resizable array.
When full, creates a new array with 1.5x capacity and copies elements.
Access: O(1), Insert/Delete middle: O(n)

✅ LinkedList
Each element is a Node with prev, next, and data.
Efficient for frequent add/remove at start or end.
Access: O(n), Insert/Delete: O(1) at ends

✅ Vector
Similar to ArrayList but synchronized.
Slower than ArrayList in single-threaded environments.

✅ Stack
Sub-class of Vector.
Has methods: push(), pop(), peek(), empty() for LIFO operations.


ArrayList<>(initialCapacity):
This sets the initial size of the internal array, not the actual size of the list.
.size() returns the number of elements added, not the capacity.


---



### ✅ 1. **ArrayList is a generic class**

* You can specify the type of elements it will store:

  ```java
  ArrayList<Integer> list = new ArrayList<>();
  ```

---

### ✅ 2. **ArrayList uses an internal array**

* Internally, `ArrayList` maintains a **regular array** to store elements.
* The size of this internal array is called **capacity**.
* You can specify **initial capacity**, e.g.:

  ```java
  ArrayList<Integer> list = new ArrayList<>(2);
  ```

---

### ✅ 3. **Size vs Capacity**

* `.size()` → number of elements currently stored.
* Capacity → length of internal array (can be larger than `.size()`).

---

### ✅ 4. **Dynamic Resizing**

* When you add more elements than the current capacity:

  * A **new internal array** is created.
  * The old array’s elements are **copied** into the new one.
  * The capacity is usually increased by **1.5x** or more.
  * The reference to the new array replaces the old one inside `ArrayList`.

---

### ✅ 5. **Reference Behavior**

* `ArrayList` object holds the reference to the internal array.
* You hold the reference to the `ArrayList` object.

  ```
  YourVariable (like 'l') → ArrayList object → Internal array
  ```

---

### ✅ 6. **What happens during resizing?**

* The internal array’s **memory address changes** (new array).
* The `ArrayList` object stays the same.
* Your reference (`l`) keeps pointing to the same `ArrayList` object.

---

### ✅ 7. **Generics in ArrayList**

* `ArrayList<T>` supports generics.
* **Only reference types** (like `Integer`, `String`) can be used.
* Primitive types (`int`, `char`) must be **wrapped** (`Integer`, `Character`) because Java generics only work with reference types.

---

### 🔁 Example:

```java
List<Integer> l = new ArrayList<>(2);
l.add(10);  // size = 1
l.add(20);  // size = 2
l.add(30);  // triggers resizing!
```

Now `ArrayList` creates a new internal array with more capacity and copies `10, 20, 30` into it.

---

✅ 1. What is LinkedList in Java?
LinkedList is a doubly linked list implementation of the List, Deque, and Queue interfaces.

java
Copy
Edit
LinkedList<String> list = new LinkedList<>();
Each node stores:

Data (element)

A pointer to the next node

A pointer to the previous node

✅ 2. Features of LinkedList
Feature	LinkedList
Type	Doubly Linked List
Performance	Fast insertion/deletion (O(1)) at ends
Slow access	Random access is slow (O(n))
Allows duplicates	✅ Yes
Null elements allowed	✅ Yes
Dynamic size	✅ Grows and shrinks automatically
Thread-safe	❌ Not synchronized

✅ 3. Internal Working
Each element in the list is represented by a Node object:

java
Copy
Edit
private static class Node<E> {
    E item;
    Node<E> next;
    Node<E> prev;
}
So when you write:

java
Copy
Edit
LinkedList<Integer> l = new LinkedList<>();
l.add(10);
l.add(20);
It creates:

csharp
Copy
Edit
null ← [10] ⇄ [20] → null
✅ 4. Common Methods
java
Copy
Edit
l.add(element);        // add at end
l.addFirst(element);   // add at front
l.addLast(element);    // add at end

l.remove();            // removes head
l.removeFirst();
l.removeLast();

l.get(index);          // get by index
l.size();              // current size
✅ 5. Comparison with ArrayList
Feature	ArrayList	LinkedList
Access	O(1)	O(n)
Insertion/Deletion at ends	Slow (O(n))	Fast (O(1))
Memory usage	Less (only data)	More (pointers)
Internal data	Array	Nodes (prev/next)


`No, in LinkedList you cannot set an initial capacity — because LinkedList is not backed by an array, unlike ArrayList.`

✅ 6. When to use LinkedList?
When you frequently insert/delete elements from start/middle/end.

When random access (like get(i)) is not needed often.


