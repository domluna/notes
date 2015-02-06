2-3-4 Tree
==========

The 2-3-4 Tree is a self-balancing data structure. It's commonly used
to implement dictionaries.

They can search, insert, delete in O(log n) time.

They are a type of **B tree**.

### Node Types

* 2-Node has 1 data element, and if non-leaf has 2 child nodes.
* 3-Node has 2 data elements, and if non-leaf has 3 child nodes.
* 4-Node has 3 data elements, and if non-leaf has 4 child nodes.

2-3-4 Trees are an isometry of red-black trees (equiv data structures!).

### Properties

* Every node holds 1, 2, or 3 data elements (leafs too).
* All leaves are the same depth (the bottom level).
* All data is kept sorted.

