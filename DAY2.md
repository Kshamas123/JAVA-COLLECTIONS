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



