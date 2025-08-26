🔹 What is Comparable?

Comparable is an interface in Java (in java.lang package).

A class implements Comparable if its objects have a natural ordering (like sorting by roll number, age, name etc.).

It has only one method:

`public int compareTo(T o);`


🔹 How does compareTo() work?

Returns 0 → both objects are equal.

Returns +ve → current object (this) is greater than the given object.

Returns -ve → current object (this) is smaller than the given object.


Natural sorting order means the class itself “knows” how it should be sorted by default.

You define one attribute (or combination) inside the compareTo() method.

So whenever you do Collections.sort(listOfObjects), Java uses that compareTo logic automatically.


🔹 What is Comparator?

Comparator is an interface in java.util package.

Used when you want custom sorting logic without modifying the class itself.

You can define multiple ways to sort the same class.

Key difference from Comparable:

Comparable → class defines one natural order.

Comparator → external logic, can have many custom orders.

🔹 How it works

Single abstract method:

`int compare(T o1, T o2);`


Interview tip

Comparable → natural ordering (inside class)

Comparator → custom ordering (outside class, flexible)

You can use lambda expressions with Comparator in Java 8+ → cleaner code.
