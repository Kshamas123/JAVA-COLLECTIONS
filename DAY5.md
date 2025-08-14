 1. What is LinkedHashSet?

LinkedHashSet is a child class of HashSet that:

Maintains a doubly-linked list running through its entries

Preserves the insertion order of elements

Still does not allow duplicates

Internally uses a LinkedHashMap

Time Complexity	O(1) for add, remove, contains (like HashSet)



    public static void main(String[] args) {
        LinkedHashSet<String> set = new LinkedHashSet<>();
        set.add("banana");
        set.add("apple");
        set.add("orange");
        set.add("banana"); // Duplicate ignored

        System.out.println(set); // Output: [banana, apple, orange]
    }


LinkedHashSet uses a LinkedHashMap under the hood:


private transient LinkedHashMap<E,Object> map;

Each element you add becomes a key in the LinkedHashMap with a dummy value (PRESENT), just like HashSet, but insertion order is recorded using a linked list.

LinkedHashSet is not thread-safe by default
