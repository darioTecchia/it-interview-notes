# Web Development

## Explain what is CORS? How does it work?
__Cross-Origin Resource Sharing__ (CORS) is an HTTP-header based mechanism that allows a server to indicate any origins (domain, scheme, or port) other than its own from which a browser should permit loading resources. CORS also relies on a mechanism by which browsers make a "preflight" request to the server hosting the cross-origin resource, in order to check that the server will permit the actual request. In that preflight, the browser sends headers that indicate the HTTP method and headers that will be used in the actual request.

## List out the advantage of HTTP/2 as compared with HTTP 1.1?
The advantage of HTTP/2 compared to HTTP/1.1 is:
- HTTP headers data compression
- Server push technologies
- Over a single TCP connection parallel loading of page elements
- Prioritization of request

## Mention some tips you can use to reduce the load time of a web application that you have written?
To decrease the load time of a web application you have to follow the following tips

- Optimize images to no longer than screen resolution and save it as a compressed file
- Eliminate all JavaScript files to reduce the amount of transferable data
- Combine & Mininify all CSS and JS and call them in footer
- Defer or Asynch JS Files
- Caching

## Mention what is the correct way to include JavaScript into your HTML?
The correct way to include JavaScript into your HTML is by using inline event handlers or inline code.

## Explain what is the difference between cookies and local storage?
||||
|--- |--- |--- |
||Cookies|Local Storage|
|Client Side/ Server Side|Data accessible both at client side and server side. The data is sent to the serverside with every cookie request.|Only at the local browser side data is accessible. Server cannot use local storage until deliberately sent a request to the server via POST or GET|
|Size|Storage capacity of cookies is 4095 bytes/cookie|Storage capacity of local storage is 5MB per domain|
|Expiration|Cookies have expiration and cookie data gets deleted after some time|There is no expiration and has to remove manually|

## Explain how can you refer to CSS file in the web page?
You can refer to the `.css` file in the webpage by using the `<link>` tag. It should be kept between `<head></head>` tags. For example `<link href=”/css/mystyle.css” type=”text/css” rel=”stylesheet”/>`.

## What is data structure?
Data structure refers to the way data is organized and manipulated. It seeks to find ways to make data access more efficient. When dealing with the data structure, we not only focus on one piece of data but the different set of data and how they can relate to one another in an organized manner.

## When is a binary search best applied?
A binary search is an algorithm that is best applied to search a list when the elements are already in order or sorted. The list is searched starting in the middle, such that if that middle value is not the target search key, it will check to see if it will continue the search on the lower half of the list or the higher half. The split and search will then continue in the same manner.

## What is a linked list?
A linked list is a sequence of nodes in which each node is connected to the node following it. This forms a chain-like link for data storage.

## What is LIFO?
LIFO is a short form of Last In First Out. It refers how data is accessed, stored and retrieved. Using this scheme, data that was stored last should be the one to be extracted first. This also means that in order to gain access to the first data, all the other data that was stored before this first data must first be retrieved and extracted.

## What is a queue?
A queue is a data structure that can simulate a list or stream of data. In this structure, new elements are inserted at one end, and existing elements are removed from the other end.

## What are binary trees?
A binary tree is one type of data structure that has two nodes, a left node, and a right node. In programming, binary trees are an extension of the linked list structures.

## Which data structures are applied when dealing with a recursive function?
Recursion, is a function that calls itself based on a terminating condition, makes use of the stack. Using LIFO, a call to a recursive function saves the return address so that it knows how to return to the calling function after the call terminates.

## What is a stack?
A stack is a data structure in which only the top element can be accessed. As data is stored in the stack, each data is pushed downward, leaving the most recently added data on top.

##  Explain Binary Search Tree
A binary search tree stores data in such a way that they can be retrieved very efficiently. The left subtree contains nodes whose keys are less than the node’s key value, while the right subtree contains nodes whose keys are greater than or equal to the node’s key value. Moreover, both subtrees are also binary search trees.

## Are linked lists considered linear or non-linear data structures?
It depends on where you intend to apply linked lists. If you based it on storage, a linked list is considered non-linear. On the other hand, if you based it on access strategies, then a linked list is considered linear.

## What is FIFO?
FIFO stands for First-in, First-out, and is used to represent how data is accessed in a queue. Data has been inserted into the queue list the longest is the one that is removed first.

## What is an ordered list?
An ordered list is a list in which each node’s position in the list is determined by the value of its key component, so that the key values form an increasing sequence, as the list is traversed.

## What is merge sort?
Merge sort, is a  divide-and-conquer approach for sorting the data. In a sequence of data, adjacent ones are merged and sorted to create bigger sorted lists. These sorted lists are then merged again to form an even bigger sorted list, which continues until you have one single sorted list.

## Differentiate NULL and VOID
Null is a value, whereas Void is a data type identifier. A variable that is given a Null value indicates an empty value. The void is used to identify pointers as having no initial size.

## What is the primary advantage of a linked list?
A linked list is an ideal data structure because it can be modified easily. This means that editing a linked list works regardless of how many elements are in the list.

## What is the difference between a PUSH and a POP?
Pushing and popping applies to the way data is stored and retrieved in a stack. A push denotes data being added to it, meaning data is being “pushed” into the stack. On the other hand, a pop denotes data retrieval, and in particular, refers to the topmost data being accessed.

## What is a linear search?
A linear search refers to the way a target key is being searched in a sequential data structure. In this method, each element in the list is checked and compared against the target key. The process is repeated until found or if the end of the file has been reached.

## How does variable declaration affect memory allocation?
The amount of memory to be allocated or reserved would depend on the data type of the variable being declared. For example, if a variable is declared to be of integer type, then 32 bits of memory storage will be reserved for that variable.

## What is the advantage of the heap over a stack?
The heap is more flexible than the stack. That’s because memory space for the heap can be dynamically allocated and de-allocated as needed. However, the memory of the heap can at times be slower when compared to that stack.

## What is Data abstraction?
Data abstraction is a powerful tool for breaking down complex data problems into manageable chunks. This is applied by initially specifying the data objects involved and the operations to be performed on these data objects without being overly concerned with how the data objects will be represented and stored in memory.

## How do you insert a new item in a binary search tree?
Assuming that the data to be inserted is a unique value (that is, not an existing entry in the tree), check first if the tree is empty. If it’s empty, just insert the new item in the root node. If it’s not empty, refer to the new item’s key. If it’s smaller than the root’s key, insert it into the root’s left subtree, otherwise, insert it into the root’s right subtree.

## How does a selection sort work for an array?
The selection sort is a fairly intuitive sorting algorithm, though not necessarily efficient. In this process, the smallest element is first located and switched with the element at subscript zero, thereby placing the smallest element in the first position.

The smallest element remaining in the subarray is then located next to subscripts 1 through n-1 and switched with the element at subscript 1, thereby placing the second smallest element in the second position. The steps are repeated in the same manner till the last element.

## How do signed and unsigned numbers affect memory?
In the case of signed numbers, the first bit is used to indicate whether positive or negative, which leaves you with one bit short. With unsigned numbers, you have all bits available for that number. The effect is best seen in the number range (an unsigned 8-bit number has a range 0-255, while the 8-bit signed number has a range -128 to +127.

## What is the minimum number of nodes that a binary tree can have?
A binary tree can have a minimum of zero nodes, which occurs when the nodes have NULL values. Furthermore, a binary tree can also have 1 or 2 nodes.

## Which sorting algorithm is considered the fastest?
There are many types of sorting algorithms: quick sort, bubble sort, balloon sort, radix sort, merge sort, etc. Not one can be considered the fastest because each algorithm is designed for a particular data structure and data set. It would depend on the data set that you would want to sort.

## What is a bubble sort and how do you perform it?
A bubble sort is one sorting technique that can be applied to data structures such as an array. It works by comparing adjacent elements and exchanges their values if they are out of order. This method lets the smaller values “bubble” to the top of the list, while the larger value sinks to the bottom.

## How does selection sort work?
Selection sort works by picking the smallest number from the list and placing it at the front. This process is repeated for the second position towards the end of the list. It is the simplest sort algorithm.

## What is a graph?
A graph is one type of data structure that contains a set of ordered pairs. These ordered pairs are also referred to as edges or arcs and are used to connect nodes where data can be stored and retrieved.

## Briefly explain recursive algorithm.
Recursive algorithm targets a problem by dividing it into smaller, manageable sub-problems. The output of one recursion after processing one sub-problem becomes the input to the next recursive process.

## How do you search for a target key in a linked list?
To find the target key in a linked list, you have to apply sequential search. Each node is traversed and compared with the target key, and if it is different, then it follows the link to the next node. This traversal continues until either the target key is found or if the last node is reached.