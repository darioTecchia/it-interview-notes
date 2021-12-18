# Searches
## Linear Search
In computer science, linear search or sequential search is a 
method for finding a target value within a list. It sequentially 
checks each element of the list for the target value until a 
match is found or until all the elements have been searched.
Linear search runs in at worst linear time and makes at most `n` 
comparisons, where `n` is the length of the list. 

![Linear Search](https://www.tutorialspoint.com/data_structures_algorithms/images/linear_search.gif)

### Complexity

**Time Complexity**: `O(n)` - since in worst case we're checking each element
exactly once.

## Binary Search
In computer science, binary search, also known as half-interval 
search, logarithmic search, or binary chop, is a search algorithm 
that finds the position of a target value within a sorted 
array. Binary search compares the target value to the middle 
element of the array; if they are unequal, the half in which 
the target cannot lie is eliminated and the search continues 
on the remaining half until it is successful. If the search 
ends with the remaining half being empty, the target is not 
in the array.

![Binary Search](https://upload.wikimedia.org/wikipedia/commons/8/83/Binary_Search_Depiction.svg)

### Complexity

**Time Complexity**: `O(log(n))` - since we split search area by two for every
next iteration.
