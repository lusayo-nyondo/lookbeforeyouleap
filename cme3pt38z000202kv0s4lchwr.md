---
title: "Leap Before You Look - A Mental Model for Data Structures and Algorithms"
datePublished: Sat Aug 09 2025 03:48:28 GMT+0000 (Coordinated Universal Time)
cuid: cme3pt38z000202kv0s4lchwr
slug: leap-before-you-look-a-mental-model-for-data-structures-and-algorithms
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1754711077183/6ce275b5-13c9-43fc-b80a-3c6cdb6bb508.png
tags: interview, algorithms, computer-science, data-structures, interview-questions, programming-tips

---

Like the title says, this article is going to be about an alternative mental model to learning about and possibly teaching data structures and algorithms. The reason I'm writing it is out of a personal gripe of mine, so allow me to tell you a bit about myself first. If you want to skip that though, you can go sthreat to “**The Mental Model**”.

Like many developers in today's landscape, I did not go through a formal education in computer science. I went to college for management information systems for a few years, barely did any math and/or theoretical programming classes, and was thrust into the world of systems administration. After about 2 years of that, I got laid off and decided instead of looking for another job in that field, I'd focus on trying to do what I always wanted to do - code for a living. I coded everyday, picked up django and react, applied for as many jobs as I could and after about 8 months, I finally got myself a job. After about 4 years of basically hovering around the same level in terms of salary, I wanted to get a better job, but found that the types of jobs that paid what I wanted to be paid required an interview process that I dreaded - what people today would call the "FAANG interview." Basically, an interview process that involves a good understanding of data structures and algorithms which I've always hesitated to really pick up.

When you're not formally trained, data structures and algorithms can be a very intimidating topic. Sure, there's lots of materials to learn online, and lots of free courses and books that offer university-level courses on them. However, that's kind of the problem - that they try to provide "university-level" style teaching, when not everyone needs to learn them in a university context.

For the working man (or woman) with limited time who last cracked open a math textbook half a decade ago, a more intuitive, get-into-details-later approach is necessary to introduce data structures and algorithms. Basically we need to "leap" into developing an intuition for solving problems using data structures and algorithms before spending time "looking" at how to analyze or even design them.

To this end, as I was studying data structures and algorithms for myself, I found I've developed a bit of a mental model that allows me to think about data structures and algorithms in a way that I think makes them more intuitive to understand. And I'm writing this article to share that approach to anyone who might be interested.

## The Mental Model

For me, it helps to look at data structures and algorithms using a conceptual framework that I'd like to call the Index-Pointer approach. It's a fun little re-classification of the concepts related to the study of data structures and algorithms. Basically, every concept related to data structures can be organized starting from the concept of indexes and pointers, and we’ll build on these definitions.

The mental model I have organizes understanding data structures and algorithms in three phases:

1. **Foundational Data Models**
    
2. **Abstract Data Types**
    
3. **Algorithmic Techniques**
    

These three serve as the building blocks for the way I understand data structures and algorithms and the way that I would teach someone if I had to tutor them. Let's get into what each of these actually mean.

1. **Foundational Data Models**
    
    So first things we need to define what exactly is a "Data Structure". For my mental model, a "Data Structure" is a way of grouping related items in a way a computer can understand.
    
    There are fundamentally two ways of grouping related items, which is what I mean when I say "Foundational Data Models". These data models are:
    
    **a. Index-based data models** \- A data model where you can know its exact size without looking at the data. You can use the data model’s preconfigured size, and known properties about its elements to infer the position of its elements.  
      
    A good example is the number of seats on a plane. You know exactly how many there are before you know how many people are actually on the plane because the plane itself is designed to have a fixed number of seats.  
      
    **b. Pointer-based data models** - A data model where you do not know its exact size until you look at all the elements in the data model. You can only use the elements themselves to infer the positions of other elements.  
      
    A good example is the number of people in, say, two generations of a family tree. You cannot know the number until you quantify how many children and siblings each individual member has. Based on those two core data models, we can then talk about the traditional data structures that we know of.
    
2. **Abstract Data Types**
    
    Now, based on those two core data models, we can now start defining abstract data types.
    
    Abstract data types are basically representations of a group of items that have logical constraints on the way the items or ordered and a contract for how to access and manipulate their individual elements.
    
      
    They are independent of the actual data model that's used to implement them. Of these, we have the examples:
    
    1. Array
        
        In normal computer science, maybe this isn't considered an ADT, but for this framework it is. An array is an ADT that defines the contract for a fixed-size collection of elements, where each element is identified by an index.
        
        * size() -&gt; Get the number of elements in the array.
            
        * insertAt(index, element) -&gt; Insert an element at a specific index. This operation may replace an existing element.
            
        * elementAt(index) -&gt; Retrieve the element at a specific index.
            
        * removeAt(index) -&gt; Remove the element at a specific index.
            
    2. Hash Map A Hash Map is an ADT that defines the contract for a collection of key-value pairs. It uses a hashing function to map keys to specific locations, allowing for very fast insertion and retrieval.
        
        * size() -&gt; Get the number of key-value pairs stored in the map.
            
        * insert(key, value) -&gt; Insert a key and its associated value into the map. If the key already exists, its value is updated.
            
        * get(key) -&gt; Retrieve the value associated with a specific key.
            
        * remove(key) -&gt; Remove a key and its associated value from the map.
            
        * containsKey(key) -&gt; Check if a given key exists in the map.
            
        * isEmpty() -&gt; Check if the map has any key-value pairs.
            
    3. Stack An ADT that defines the contract for a collection of elements with a Last-In, First-Out (LIFO) access pattern.
        
        * push(element) -&gt; Add an element to the top of the stack.
            
        * pop() -&gt; Remove and return the element at the top of the stack.
            
        * peek() -&gt; Return the element at the top of the stack without removing it.
            
        * isEmpty() -&gt; Check if the stack is empty.
            
    4. Queue An ADT that defines the contract for a collection of elements with a First-In, First-Out (FIFO) access pattern.
        
        * enqueue(element) -&gt; Add an element to the back (or tail) of the queue.
            
        * dequeue() -&gt; Remove and return the element from the front (or head) of the queue.
            
        * peek() -&gt; Return the element from the front of the queue without removing it.
            
        * isEmpty() -&gt; Check if the queue is empty.
            
    5. Linked List An ADT that defines the contract for a sequence of elements where each element points to the next one. This ADT can be implemented using either a singly or doubly linked list model.
        
        * insertFirst(element) -&gt; Add an element to the beginning of the list.
            
        * insertLast(element) -&gt; Add an element to the end of the list.
            
        * removeFirst() -&gt; Remove and return the element at the beginning of the list.
            
        * removeLast() -&gt; Remove and return the element at the end of the list.
            
        * size() -&gt; Get the number of elements in the list.
            
        * isEmpty() -&gt; Check if the list is empty.
            
    6. Tree An ADT that defines the contract for a hierarchical data structure with a root node and child nodes. A tree has no cycles and a single path between any two nodes.
        
        * insert(element) -&gt; Add an element to the tree in the correct position based on its value (for a Binary Search Tree) or a specific constraint.
            
        * remove(element) -&gt; Remove an element from the tree.
            
        * search(element) -&gt; Find and return a node containing the specified element.
            
        * traverse() -&gt; Visit all nodes in the tree in a specific order (e.g., in-order, pre-order, post-order).
            
    7. Graph An ADT that defines the contract for a collection of nodes (vertices) and the connections (edges) between them. Unlike a tree, a graph can contain cycles.
        
        * addVertex(vertex) -&gt; Add a vertex to the graph.
            
        * addEdge(from, to) -&gt; Add an edge connecting a from vertex to a to vertex. This can be a directed or undirected edge.
            
        * removeVertex(vertex) -&gt; Remove a vertex and all associated edges from the graph.
            
        * removeEdge(from, to) -&gt; Remove the edge connecting the from and to vertices.
            
        * hasPath(from, to) -&gt; Determine if a path exists between two vertices.
            
    8. Heap A Heap is an ADT that defines the contract for a specialized tree-based data structure where the parent node is either always greater than or equal to (a Max-Heap) or less than or equal to (a Min-Heap) its children.
        
        The heap is special because its underlying logical structure as a "complete" binary tree allows it to be efficiently implemented using an index-based data structure, like an array, even though its conceptual contract is pointer-based.
        
        * insert(element) -&gt; Add an element to the heap and rebalance it.
            
        * peek() -&gt; Return the root element of the heap (the maximum in a Max-Heap or the minimum in a Min-Heap) without removing it.
            
        * extractMax() or extractMin() -&gt; Remove and return the root element of the heap, then reorganize the heap to maintain the heap invariant.
            
        * isEmpty() -&gt; Check if the heap has any elements.
            
        * size() -&gt; Get the number of elements in the heap.
            
        * build(array) -&gt; Create a heap from an unsorted array of elements in an efficient manner.
            

In addition to those above, we also have definitions for other ADTs which add additonal constraints. For example, a Binary Tree is an ADT that basically has the contract of a Tree but also enforces that each node can have at most two children. We can make definitions for AVL Trees, Red-Black Trees, and so on and so forth. I don't want to get bogged down here, but the key idea is to build upon this. So let's move on to the third part of this mental model.

3. **Algorithmic Techniques**
    

In this mental model, we can define algorithmic techniques as an ordered set of computational operations we perform directly on the underlying data of an Abstract Data Type to produce a new value.

So that this definition holds, I like to think of it as all abstract data types are immutable. So even when you "sort an array" for example, you're not sorting the original array, you're creating a new sorted array from your original array. Just for the purposes of the mental model, though I'm open to hear any criticism on this.

Algorithmic techniques broadly fall into four categories.

1. Navigation Techniques  
    Navigation is the process of moving through a data structure to access its elements. This is the most fundamental of all techniques.  
      
    Examples:
    
    * Array Traversal: Iterating through an array using a for loop from index 0 to n-1. This is a classic example of index-based navigation.
        
    * Linked List Traversal: Starting at the head of a linked list and following the next pointers until you reach the end. This is a primary example of pointer-based navigation.
        
    * Tree Search: Performing a Depth-First Search (DFS) or Breadth-First Search (BFS) to visit every node in a tree or graph.
        
2. Precomputation Techniques  
    Precomputation is doing work ahead of time to make future operations faster. It's an investment of time now for a return of speed later.  
      
    Examples:
    
    * Sorting: Arranging the elements of a list or array in a specific order. Once sorted, operations like searching become much faster.
        
    * Hashing: Creating a hash table from a list of items to allow for near-constant-time querying. - Prefix Sum Array: Creating a new array where each element stores the sum of all elements before it in the original array. This allows you to compute the sum of a range in constant time.
        
3. Querying Techniques  
    Querying is the act of answering a question about the underlying data. The answer is typically a boolean (true/false) or a specific value or range of values.  
      
    Examples:
    
    * contains(element): Checking if a data structure holds a specific element.
        
    * find(element): Locating and returning the index or position of an element.
        
    * isEmpty(): A query that checks if the data structure has any elements.
        
    * min() or max(): Finding the smallest or largest value in a data structure.
        
4. Computation Techniques  
    Computation is the process of creating a new value from the existing data. This can be a simple calculation or a complex aggregation.  
      
    Examples:
    
    * sum(): Calculating the sum of all elements in an array.
        
    * average(): Computing the mean value of a set of numbers.
        
    * transpose(matrix): Creating a new matrix by flipping the rows and columns of an original.
        
    * merge(list1, list2): Creating a single new list by combining the elements of two lists.
        

Each "algorithm" is essentially a collection of navigations, precomputations, queries, and/or computations that you perform on abstract data types until you produce the value you want.

## Common Algorithms Using the Index-Pointer Mental Model

Here are some well-known algorithms kind of broken down using this mental model:

1. **Binary Search Underlying Data Model: Index-based (most typically an array, could be a hashmap too).**
    

Techniques:

Precomputation: The algorithm assumes the array is already sorted. If not, sorting is a necessary precomputation step.

Navigation: It uses two "pointers" (low and high indices) to navigate the array. The pointers are not physically stored in the data model but are computational artifacts.

Querying: It performs a query at the midpoint of the current search space (is the target greater than the middle element?).

Computation: Based on the query, it computes the new values for low or high to reduce the search space.

2. **Breadth-First Search (BFS) BFS is a traversal algorithm that finds the shortest path between nodes in an unweighted graph or tree.**
    

Underlying Data Model: Pointer-based (nodes and edges).

Techniques:

Data Structures: It uses a Queue ADT to manage the nodes it needs to visit. This ADT is often implemented with a pointer-based data model (a linked list).

Navigation: It starts at a source node and navigates to all of its immediate neighbors, then all of their neighbors, and so on.

Querying: It performs a crucial query: has this node already been visited? to avoid cycles.

Precomputation: It precomputes a visited set to store nodes it has already processed, which is a form of caching.

3. **Merge Sort Underlying Data Model: Index-based (the arrays).**
    

Techniques: Precomputation: The algorithm's core is a recursive precomputation. It continuously splits the original array and "precomputes" sorted subarrays until it reaches the base case of a single element.

Computation: The core of the algorithm is the merge function, which takes two sorted subarrays and creates a brand new, single sorted array from them. It computes a new value from two existing values.

Navigation: It performs navigation within two separate subarrays simultaneously, using two pointers to compare and select elements for the new, merged array.

## Summary

So yeah, that is the gist of the mental model for algorithms that I've been cooking up in my head. I hope this has been an interesting read for you. I'm still learning more about data structures and algorithms, and while I'm on my journey, I gravitated towards this taxonomy as a better way of being introduced to data structures and algorithms if you want to understand what exactly is going on with algorithms before you start thinking about time-complexity and space-complexity and all that stuff.

If you've made it this far, thank you very much. I'd love to hear your feedback on this. I'm planning on turning this mental model into an ebook or a website, and would love to hear any feedback if you've got any criticisms or would like to collaborate.

Have a great weekend!