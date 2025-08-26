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
