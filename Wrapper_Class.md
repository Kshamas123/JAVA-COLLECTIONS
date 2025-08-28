What are wrapper classes?

Java has primitive types (lightweight, not objects) and wrapper classes (object versions of primitives).

Primitive	Wrapper class

byte - Byte

short	- Short

int	- Integer

long - Long

float	- Float

double	- Double

char - Character

boolean	- Boolean

Why wrappers?

Collections & generics need objects (e.g., List<Integer>, not List<int>).

Provide utility methods: parsing, comparing, constants (MAX_VALUE), etc.

Autoboxing and unboxing are features introduced in Java SE 5 that provide automatic conversions between primitive data types and their corresponding wrapper class objects. This simplifies code by eliminating the need for explicit type casting in many scenarios.

Autoboxing:

Autoboxing is the automatic conversion of a primitive data type into an object of its corresponding wrapper class. For example, when an int primitive is used in a context that expects an Integer object, the Java compiler automatically converts the int to an Integer.

`Integer myInteger = 10; // Autoboxing: int primitive 10 is converted to an Integer object`

Unboxing:

Unboxing is the reverse process of autoboxing. It is the automatic conversion of an object of a wrapper class into its corresponding primitive data type. For example, when an Integer object is used in a context that expects an int primitive, the Java compiler automatically extracts the int value from the Integer object.

`Integer myInteger = 25;
int myPrimitive = myInteger; // Unboxing: Integer object myInteger is converted to an int primitive`

Danger: Unboxing a null throws NullPointerException.

Integer k = null;
int v = k;   // NPE here

🔹 Wrapper classes caching (Integer, Short, Byte, Long, Character)

In Java, wrapper classes (like Integer, Long, etc.) sometimes don’t create a new object each time you use them. Instead, Java reuses (caches) objects for certain values to save memory and improve performance.

public class WrapperCacheDemo {
    public static void main(String[] args) {
        Integer a = 100;
        Integer b = 100;

        Integer x = 200;
        Integer y = 200;

        System.out.println(a == b); // true (same object from cache)
        System.out.println(x == y); // false (different objects)
    }
}

For Integer, values between -128 and 127 are cached.

So when you use Integer.valueOf(100), Java reuses the same object for 100.

But for 200, Java creates a new object each time → so x == y is false.

📌 Other wrapper classes with caching:

Byte: all values (-128 to 127) are cached.

Short: -128 to 127 are cached.

Integer: -128 to 127 are cached.

Long: -128 to 127 are cached.

Character: 0 to 127 are cached.

Boolean: only true and false (obviously cached).

Float and Double do not cache values.

Why caching?

Because:

Small numbers are very commonly used.

Reusing the same objects saves memory.

It also improves performance by avoiding unnecessary new object creation.

👉 Important: This works only with autoboxing / valueOf(). If you explicitly use new, a new object is always created.

Integer a = new Integer(100);

Integer b = new Integer(100);

System.out.println(a == b); // false (new objects always)
