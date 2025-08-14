TreeSet in Java (java.util.TreeSet)

TreeSet is a sorted, unique, and navigable set implementation that stores elements in natural order (ascending) or by a custom comparator.

TreeSet<Integer> set = new TreeSet<>();

KEY PROPERTIES

1.Duplicate values are not allowed

2.Null elements are not allowed

3.Elements maintain sorted order

RED BLACK TREE is a underlying structure of Treeset.

A Red-Black Tree is a type of self-balancing binary search tree (BST).

It maintains a special set of color rules (red/black) on each node to ensure the tree stays approximately balanced, which keeps operations like add(), remove(), and search() efficient — all in O(log n) time.


Rules of a Red-Black Tree:

Every node is either red or black, and the tree maintains these 5 properties:

Every node is either red or black.

The root is always black.

Red nodes can’t have red children (no two reds in a row).

Every path from a node to its descendant null nodes must have the same number of black nodes (black-height).

New nodes are always added as red.

What Happens During Insertion in RED BLACK TREE?

Insert node as red

Check rules:

If there's a red-red violation, fix it using:

Recoloring (if uncle is red)

Rotation (left/right) and recoloring (if uncle is black)

After fixing, root is made black

This process keeps the tree balanced.
