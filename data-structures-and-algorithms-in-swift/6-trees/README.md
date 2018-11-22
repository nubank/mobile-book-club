## Trees
Trees are data structures used to represent hierarchical relationships, and its applications and types are various.

```
  O
 / \
O   O
  / | \
 O  O  O
```

### Terminology

It is important that we know to name the elements so we can have better understanding when studying algorithms on trees.
Here are the names to the faces:

#### Node

A node is the unit structure that composes a tree.
A node contains a piece of data, like an `Int` or any kind of custom data you might have.
Also, each node has references to other nodes, normally called `children nodes`.

#### Parent, children

These commonly-seen-terms are used to explain the relation between adjacent nodes.
If a node has a direct reference to other node, we call the referenced one its child.
Analogously, the node which has a reference to another is called a parent.

```
  O <- parent
 / \
O   O <- children
```

A node can have only one parent, but multiple children.

#### Root

The one node without a parent in a tree is called the `root` node, and each tree has a single root.

```
  O <- root
 / \
O   O
```

#### Leaf

Leaf nodes are the ones without children.

```
          O
         / \
leaf -> O   O
            |
            O <- leaf
```

### Traversal algorithms

There are two main ways of traversing a tree, `depth-first` and `level-order`.

> Here, the nodes are represented with numbers, which shows the order of traversal.

#### Depth-first traversal

Depth-first traversal visits one **branch** at a time, from root to leaves:

```
     1
   /   \
  2     4
 /    / | \
3    5  6  8
        |
        7
```

#### Level-order traversal

Level-order traversal visits one **level** at a time:

```
     1
   /   \
  2     3
 /    / | \
4    5  6  7
        |
        8
```

In a depth-first traversal, the nodes would be visited in that order, counting from 1 to 7.

### Search

Search algorithm is straightforward now we know the behavior of the traversal ones.
All we have to do is check if the element we are looking for is the current one while traversing.
