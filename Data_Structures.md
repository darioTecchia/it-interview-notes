# Data Structures

> I suggest you to take a look at __trekhleb__'s repo: [javascript-algorithms](https://github.com/trekhleb/javascript-algorithms).

## Linked List
In computer science, a **linked list** is a linear collection
of data elements, in which linear order is not given by
their physical placement in memory. Instead, each
element points to the next. It is a data structure
consisting of a group of nodes which together represent
a sequence. Under the simplest form, each node is
composed of data and a reference (in other words,
a link) to the next node in the sequence. This structure
allows for efficient insertion or removal of elements
from any position in the sequence during iteration.
More complex variants add additional links, allowing
efficient insertion or removal from arbitrary element
references. A drawback of linked lists is that access
time is linear (and difficult to pipeline). Faster
access, such as random access, is not feasible. Arrays
have better cache locality as compared to linked lists.

![Linked List](https://upload.wikimedia.org/wikipedia/commons/6/6d/Singly-linked-list.svg)

### Pseudocode for Basic Operations

#### Insert
```text
Add(value)
  Pre: value is the value to add to the list
  Post: value has been placed at the tail of the list
  n ← node(value)
  if head = ø
    head ← n
    tail ← n
  else
    tail.next ← n
    tail ← n
  end if
end Add
```

```text
Prepend(value)
 Pre: value is the value to add to the list
 Post: value has been placed at the head of the list
 n ← node(value)
 n.next ← head
 head ← n
 if tail = ø
   tail ← n
 end
end Prepend
```

#### Search
```text
Contains(head, value)
  Pre: head is the head node in the list
       value is the value to search for
  Post: the item is either in the linked list, true; otherwise false
  n ← head
  while n != ø and n.value != value
    n ← n.next
  end while
  if n = ø
    return false
  end if
  return true
end Contains
```

#### Delete
```text
Remove(head, value)
  Pre: head is the head node in the list
       value is the value to remove from the list
  Post: value is removed from the list, true, otherwise false
  if head = ø
    return false
  end if
  n ← head
  if n.value = value
    if head = tail
      head ← ø
      tail ← ø
    else
      head ← head.next
    end if
    return true
  end if
  while n.next != ø and n.next.value != value
    n ← n.next
  end while
  if n.next != ø
    if n.next = tail
      tail ← n
      tail.next = null
    end if
    n.next ← n.next.next
    return true
  end if
  return false
end Remove
```

#### Traverse
```text
Traverse(head)
  Pre: head is the head node in the list
  Post: the items in the list have been traversed
  n ← head
  while n != ø
    yield n.value
    n ← n.next
  end while
end Traverse
```

#### Traverse in Reverse
```text
ReverseTraversal(head, tail)
  Pre: head and tail belong to the same list
  Post: the items in the list have been traversed in reverse order
  if tail != ø
    curr ← tail
    while curr != head
      prev ← head
      while prev.next != curr
        prev ← prev.next
      end while
      yield curr.value
      curr ← prev
    end while
   yield curr.value
  end if
end ReverseTraversal
```

### Complexities

#### Time Complexity
| Access    | Search    | Insertion | Deletion  |
| :-------: | :-------: | :-------: | :-------: |
| O(n)      | O(n)      | O(1)      | O(n)      |

#### Space Complexity
O(n)

## Queue
In computer science, a **queue** is a particular kind of abstract data 
type or collection in which the entities in the collection are 
kept in order and the principle (or only) operations on the 
collection are the addition of entities to the rear terminal 
position, known as enqueue, and removal of entities from the 
front terminal position, known as dequeue. This makes the queue 
a First-In-First-Out (FIFO) data structure. In a FIFO data 
structure, the first element added to the queue will be the 
first one to be removed. This is equivalent to the requirement 
that once a new element is added, all elements that were added 
before have to be removed before the new element can be removed. 
Often a peek or front operation is also entered, returning the 
value of the front element without dequeuing it. A queue is an 
example of a linear data structure, or more abstractly a 
sequential collection.

Representation of a FIFO (first in, first out) queue

![Queue](https://upload.wikimedia.org/wikipedia/commons/5/52/Data_Queue.svg)

## Stack
In computer science, a **stack** is an abstract data type that serves 
as a collection of elements, with two principal operations:

* **push**, which adds an element to the collection, and
* **pop**, which removes the most recently added element that was not yet removed.

The order in which elements come off a stack gives rise to its 
alternative name, LIFO (last in, first out). Additionally, a 
peek operation may give access to the top without modifying 
the stack. The name "stack" for this type of structure comes 
from the analogy to a set of physical items stacked on top of 
each other, which makes it easy to take an item off the top 
of the stack, while getting to an item deeper in the stack 
may require taking off multiple other items first.

Simple representation of a stack runtime with push and pop operations.

![Stack](https://upload.wikimedia.org/wikipedia/commons/b/b4/Lifo_stack.png)

## Hash Table
In computing, a **hash table** (hash map) is a data 
structure which implements an *associative array* 
abstract data type, a structure that can *map keys 
to values*. A hash table uses a *hash function* to 
compute an index into an array of buckets or slots, 
from which the desired value can be found

Ideally, the hash function will assign each key to a 
unique bucket, but most hash table designs employ an 
imperfect hash function, which might cause hash 
collisions where the hash function generates the same
index for more than one key. Such collisions must be
accommodated in some way.

![Hash Table](https://upload.wikimedia.org/wikipedia/commons/7/7d/Hash_table_3_1_1_0_1_0_0_SP.svg)

Hash collision resolved by separate chaining.

![Hash Collision](https://upload.wikimedia.org/wikipedia/commons/d/d0/Hash_table_5_0_1_1_1_1_1_LL.svg)

## Heap
In computer science, a **heap** is a specialized tree-based 
data structure that satisfies the heap property described
below.

In a *min heap*, if `P` is a parent node of `C`, then the
key (the value) of `P` is less than or equal to the
key of `C`.

![MinHeap](https://upload.wikimedia.org/wikipedia/commons/6/69/Min-heap.png)

In a *max heap*, the key of `P` is greater than or equal
to the key of `C`

![Heap](https://upload.wikimedia.org/wikipedia/commons/3/38/Max-Heap.svg)

The node at the "top" of the heap with no parents is 
called the root node.

## Priority Queue
In computer science, a **priority queue** is an abstract data type 
which is like a regular queue or stack data structure, but where 
additionally each element has a "priority" associated with it. 
In a priority queue, an element with high priority is served before 
an element with low priority. If two elements have the same 
priority, they are served according to their order in the queue.

While priority queues are often implemented with heaps, they are 
conceptually distinct from heaps. A priority queue is an abstract 
concept like "a list" or "a map"; just as a list can be implemented
with a linked list or an array, a priority queue can be implemented
with a heap or a variety of other methods such as an unordered 
array.

## Tree
In computer science, a **tree** is a widely used abstract data 
type (ADT) — or data structure implementing this ADT—that 
simulates a hierarchical tree structure, with a root value 
and subtrees of children with a parent node, represented as 
a set of linked nodes.

A tree data structure can be defined recursively (locally) 
as a collection of nodes (starting at a root node), where 
each node is a data structure consisting of a value, 
together with a list of references to nodes (the "children"), 
with the constraints that no reference is duplicated, and none 
points to the root.

A simple unordered tree; in this diagram, the node labeled 7 has
two children, labeled 2 and 6, and one parent, labeled 2. The
root node, at the top, has no parent.

![Tree](https://upload.wikimedia.org/wikipedia/commons/f/f7/Binary_tree.svg)

## Binary Search Tree
In computer science, **binary search trees** (BST), sometimes called 
ordered or sorted binary trees, are a particular type of container: 
data structures that store "items" (such as numbers, names etc.) 
in memory. They allow fast lookup, addition and removal of 
items, and can be used to implement either dynamic sets of 
items, or lookup tables that allow finding an item by its key 
(e.g., finding the phone number of a person by name).

Binary search trees keep their keys in sorted order, so that lookup 
and other operations can use the principle of binary search: 
when looking for a key in a tree (or a place to insert a new key), 
they traverse the tree from root to leaf, making comparisons to 
keys stored in the nodes of the tree and deciding, on the basis 
of the comparison, to continue searching in the left or right 
subtrees. On average, this means that each comparison allows 
the operations to skip about half of the tree, so that each 
lookup, insertion or deletion takes time proportional to the 
logarithm of the number of items stored in the tree. This is 
much better than the linear time required to find items by key 
in an (unsorted) array, but slower than the corresponding 
operations on hash tables.

A binary search tree of size 9 and depth 3, with 8 at the root.
The leaves are not drawn.

![Binary Search Tree](https://upload.wikimedia.org/wikipedia/commons/d/da/Binary_search_tree.svg)

### Pseudocode for Basic Operations

#### Insertion

```text
insert(value)
  Pre: value has passed custom type checks for type T
  Post: value has been placed in the correct location in the tree
  if root = ø
    root ← node(value)
  else
    insertNode(root, value)
  end if
end insert
```
    
```text
insertNode(current, value)
  Pre: current is the node to start from
  Post: value has been placed in the correct location in the tree
  if value < current.value
    if current.left = ø
      current.left ← node(value)
    else
      InsertNode(current.left, value)
    end if
  else
    if current.right = ø
      current.right ← node(value)
    else
      InsertNode(current.right, value)
    end if
  end if
end insertNode
```

#### Searching

```text
contains(root, value)
  Pre: root is the root node of the tree, value is what we would like to locate
  Post: value is either located or not
  if root = ø
    return false
  end if
  if root.value = value
    return true
  else if value < root.value
    return contains(root.left, value)
  else
    return contains(root.right, value)
  end if
end contains
```
    
     
#### Deletion

```text
remove(value)
  Pre: value is the value of the node to remove, root is the node of the BST
      count is the number of items in the BST
  Post: node with value is removed if found in which case yields true, otherwise false
  nodeToRemove ← findNode(value)
  if nodeToRemove = ø
    return false
  end if
  parent ← findParent(value)
  if count = 1
    root ← ø
  else if nodeToRemove.left = ø and nodeToRemove.right = ø
    if nodeToRemove.value < parent.value
      parent.left ←  nodeToRemove.right
    else
      parent.right ← nodeToRemove.right
    end if
  else if nodeToRemove.left != ø and nodeToRemove.right != ø
    next ← nodeToRemove.right
    while next.left != ø
      next ← next.left
    end while
    if next != nodeToRemove.right
      remove(next.value)
      nodeToRemove.value ← next.value
    else
      nodeToRemove.value ← next.value
      nodeToRemove.right ← nodeToRemove.right.right
    end if
  else
    if nodeToRemove.left = ø
      next ← nodeToRemove.right
    else
      next ← nodeToRemove.left
    end if
    if root = nodeToRemove
      root = next
    else if parent.left = nodeToRemove
      parent.left = next
    else if parent.right = nodeToRemove
      parent.right = next
    end if
  end if
  count ← count - 1
  return true
end remove
```

#### Find Parent of Node

```text
findParent(value, root)
  Pre: value is the value of the node we want to find the parent of
       root is the root node of the BST and is != ø
  Post: a reference to the prent node of value if found; otherwise ø
  if value = root.value
    return ø
  end if
  if value < root.value
    if root.left = ø
      return ø
    else if root.left.value = value
      return root
    else
      return findParent(value, root.left)
    end if
  else
    if root.right = ø
      return ø
    else if root.right.value = value
      return root
    else
      return findParent(value, root.right)
    end if
  end if
end findParent
```

#### Find Node

```text
findNode(root, value)
  Pre: value is the value of the node we want to find the parent of
       root is the root node of the BST
  Post: a reference to the node of value if found; otherwise ø
  if root = ø
    return ø
  end if
  if root.value = value
    return root
  else if value < root.value
    return findNode(root.left, value)
  else
    return findNode(root.right, value)
  end if
end findNode
```
    
#### Find Minimum

```text
findMin(root)
  Pre: root is the root node of the BST
    root = ø
  Post: the smallest value in the BST is located
  if root.left = ø
    return root.value
  end if
  findMin(root.left)
end findMin
```
    
#### Find Maximum

```text
findMax(root)
  Pre: root is the root node of the BST
    root = ø
  Post: the largest value in the BST is located
  if root.right = ø
    return root.value
  end if
  findMax(root.right)
end findMax
```
    
#### Traversal

###### InOrder Traversal

```text
inorder(root)
  Pre: root is the root node of the BST
  Post: the nodes in the BST have been visited in inorder
  if root != ø
    inorder(root.left)
    yield root.value
    inorder(root.right)
  end if
end inorder
```

###### PreOrder Traversal

```text
preorder(root)
  Pre: root is the root node of the BST
  Post: the nodes in the BST have been visited in preorder
  if root != ø
    yield root.value
    preorder(root.left)
    preorder(root.right)
  end if
end preorder
```
   
###### PostOrder Traversal

```text
postorder(root)
  Pre: root is the root node of the BST
  Post: the nodes in the BST have been visited in postorder
  if root != ø
    postorder(root.left)
    postorder(root.right)
    yield root.value
  end if
end postorder
```
     
### Complexities

#### Time Complexity

| Access    | Search    | Insertion | Deletion  |
| :-------: | :-------: | :-------: | :-------: |
| O(log(n)) | O(log(n)) | O(log(n)) | O(log(n)) |

#### Space Complexity

O(n)

## Graph
In computer science, a **graph** is an abstract data type 
that is meant to implement the undirected graph and 
directed graph concepts from mathematics, specifically
the field of graph theory

A graph data structure consists of a finite (and possibly 
mutable) set of vertices or nodes or points, together 
with a set of unordered pairs of these vertices for an 
undirected graph or a set of ordered pairs for a 
directed graph. These pairs are known as edges, arcs, 
or lines for an undirected graph and as arrows, 
directed edges, directed arcs, or directed lines 
for a directed graph. The vertices may be part of 
the graph structure, or may be external entities 
represented by integer indices or references.

![Graph](https://www.tutorialspoint.com/data_structures_algorithms/images/graph.jpg)