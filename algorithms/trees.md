# Trees
## Depth-First Search (DFS)
Depth-first search (DFS) is an algorithm for traversing or 
searching tree or graph data structures. One starts at 
the root (selecting some arbitrary node as the root in 
the case of a graph) and explores as far as possible 
along each branch before backtracking.

![Algorithm Visualization](https://upload.wikimedia.org/wikipedia/commons/7/7f/Depth-First-Search.gif)

## Breadth-First Search (BFS)
Breadth-first search (BFS) is an algorithm for traversing 
or searching tree or graph data structures. It starts at
the tree root (or some arbitrary node of a graph, sometimes 
referred to as a 'search key') and explores the neighbor
nodes first, before moving to the next level neighbors.

![Algorithm Visualization](https://upload.wikimedia.org/wikipedia/commons/5/5d/Breadth-First-Search-Algorithm.gif)

### Pseudocode

```text
BFS(root)
  Pre: root is the node of the BST
  Post: the nodes in the BST have been visited in breadth first order
  q ← queue
  while root = ø
    yield root.value
    if root.left = ø
      q.enqueue(root.left)
    end if
    if root.right = ø
      q.enqueue(root.right)
    end if
    if !q.isEmpty()
      root ← q.dequeue()
    else
      root ← ø
    end if
  end while
end BFS
```
