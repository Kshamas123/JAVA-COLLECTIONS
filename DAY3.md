1. Vector in Java
   
Definition:
Vector is a growable array-like data structure, just like ArrayList, but it is synchronized, making it thread-safe.

`Vector<Integer> v = new Vector<>();`

Key Properties:

Feature	Vector

Implements	List, RandomAccess, Cloneable, Serializable

Underlying structure	Array

Thread-Safe	✅ Yes (uses synchronization)

Performance	❌ Slower than ArrayList in single-threaded scenarios

Initial Capacity	Default is 10

Capacity Growth	Grows by doubling the capacity


In Vector ,we can get the current capacity using:

`Vector<Integer> v = new Vector<>();
System.out.println(v.capacity());  // Default 10`


2. Stack in Java
   
Definition:

Stack is a subclass of Vector, and it follows the LIFO (Last In, First Out) principle.

`Stack<Integer> stack = new Stack<>();`

Key Stack Methods:


push(E):Add element to the top

pop():Remove and return top element

peek():View top element without removing it

empty():Check if stack is empty

search(E):Returns position from top (1-based) or -1



