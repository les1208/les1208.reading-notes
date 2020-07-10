## Implementation: Linked Lists

#### What is a Linked List?
- A Linked List is a sequence of Nodes that are connected/linked to each other. 
The most defining feature of a Linked List is that each Node references the next Node in the link.
- There are two types of Linked List - Singly and Doubly. We will be implementing a Singly Linked List in this implementation.

#### Terminology:
- Linked List: A data structure that contains nodes that links/points to the next node in the list.
- Singly: Singly refers to the number of references the node has.
Singly linked list means that there is only one reference, and the reference points to the Next node in a linked list.
- Doubly:  Doubly refers to there being two (double) references within the node. 
A Doubly linked list means that there is a reference to both the Next and Previous node.
- Node: Nodes are the individual items/links that live in a linked list. Each node contains the data for each link.
- Next: Each node contains a property called Next. This property contains the reference to the next node.
- Head: The Head is a reference type of type Node to the first node in a linked list.
- Current: The Current reference is a reference type of type Node that is currently being looked at. 
This node is traditionally used when traversing through a full linked list. 
When traversing, you typically reset the current to the head to guarantee you are starting from the beginning of the linked list.

#### Traversal
- When traversing a linked list, you are not able to use a foreach or for loop. 
We depend on the Next value in each node to guide us where the next reference is pointing. 
The Next property is exceptionally important because it will lead us where the next node is and allow us to extract the data appropriately.
- The best way to approach a traversal is through the use of a while() loop. 
This allows us to continually check that the Next node in the list is not null. 
If we accidentally end up trying to traverse on a node that is null, a NullReferenceException gets thrown and our program will crash/end.
- When traversing through a linked list, the Current node is the most helpful. 
The Current will tell us where exactly in the linked list we are and will allow us to move/traverse forward until we hit the end.

#### Big O
The Big O of time for Includes would be O(n). This is because, at its worse case, the node we are looking for will be the very last node in the linked list. n represents the number of nodes in the linked list.

The Big O of space for Includes would be O(1). This is because there is no additional space being used than what is already given to us with the linked list input.

#### Adding a Node
- Adding O(1)
Order of operations is extremely important when it comes to working with a Linked List. 
What I mean by this is you must be careful that all references to each link/node is properly assigned.

- An example can be with adding a node to a linked list. If we want to add a node with an O(1) efficiency, we have to replace the current Head of the linked list with the new node, without losing the reference to the next node in the list.

- Here are the required steps to add a new node with an O(1) efficiency.
Set Current equal to Head. This will guarantee us that we are starting from the very beginning.
We can then instantiate the new node that we are adding. 
The values passed in as arguments into the Add() method will define what the value of the Node will be.

#### Prerequisites
- When constructing your code, a few things to keep in mind.

- When making your Node class, consider requiring a value to be passed in to require that each node has a value.

- When making a Linked List, you may want to require that at least one node gets passed in upon instantiation. 
This first node is what your Head and Current will point too.

https://medium.com/basecs/whats-a-linked-list-anyway-part-1-d8b7e6508b9d
- One characteristic of linked lists is that they are linear data structures, which means that there is a sequence and an order to how they are constructed and traversed. 
We can think of a linear data structure like a game of hopscotch: in order to get to the end of the list, we have to go through all of the items in the list in order, or sequentially. 
Linear structures, however, are the opposite of non-linear structures. In non-linear data structures, items don’t have to be arranged in order, which means that we could traverse the data structure non-sequentially.
##### Memory Management 
- When an array is created, it needs a certain amount of memory. If we had 7 letters that we needed to store in an array, we would need 7 bytes of memory to represent that array. But, we’d need all of that memory in one contiguous block. That is to say, our computer would need to locate 7 bytes of memory that was free, one byte next to the another, all together, in one place.
On the other hand, when a linked list is born, it doesn’t need 7 bytes of memory all in one place. One byte could live somewhere, while the next byte could be stored in another place in memory altogether! Linked lists don’t need to take up a single block of memory; instead, the memory that they use can be scattered throughout.
