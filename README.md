# LINKED-LIST-IMPLEMENTATION

A singly linked list is one of the foundational data structures in computer science, widely used due to its dynamic nature and efficient memory management. Implementing it in C using struct showcases not only its internal mechanics but also the power of pointers and memory handling in low-level programming. Unlike arrays, singly linked lists don't require contiguous memory allocation, making them ideal for scenarios where memory usage must be flexible and dynamic.

# Structure and Core Concept
In C, a singly linked list is formed using a self-referential struct, where each node contains two primary components:
- Data: The actual information stored in the node, usually of a predefined type like int, char, or even more complex types.
- Next Pointer: A pointer to the next node in the sequence.
The list begins with a special pointer called the head, which points to the first node in the list. If the list is empty, the head is set to NULL. Each node points to the next one, and the last node in the list points to NULL, indicating the end.

# Insertion Operations
Insertion into a singly linked list can occur at various positions, each with its own logic and purpose:
- At the Beginning: This is one of the simplest insertions. A new node is created, its next is set to the current head, and then the head pointer is updated to point to the new node. This operation is constant time, O(1).
- At the End: To insert at the end, you need to traverse the entire list until you find the last node (where next == NULL). A new node is created, and the last node’s next pointer is updated to point to it. This takes linear time, O(n), where n is the number of nodes.
- In the Middle (After a Given Node): This involves adjusting the next pointers so that the new node fits in right after a specific node. This requires a search and a pointer swap, and is commonly used in more complex applications like maintaining sorted order.

# Deletion Operations
Deleting a node in a singly linked list requires careful pointer manipulation to maintain the chain. There are several cases to handle:
- From the Beginning: The head node is removed by updating the head pointer to point to the next node, and then freeing the memory of the original head.
- From the End: This requires traversing the list to find the second-last node (the one before the end), setting its next to NULL, and freeing the memory of the last node. Since there's no backward reference, this can't be done in constant time.
- From the Middle: The node to be deleted must be located by traversing the list. Once found, the previous node's next pointer is updated to skip over the deleted node, and the memory is deallocated.
In all deletion cases, memory leaks must be carefully avoided, which means every removed node must be explicitly deallocated using free() in C.

# Traversal
Traversal is the most fundamental operation used to iterate over elements in the list. Starting from the head, the list is walked node-by-node using the next pointer until NULL is reached. This is often used for:
- Printing the contents of the list.
- Searching for a value.
- Counting nodes.
Traversal is inherently linear, O(n), and it gives insight into the list’s structure at any given time. It’s also essential for debugging and validating insertions or deletions.

# Why Use Singly Linked Lists?
While arrays are great for direct indexing, singly linked lists shine where frequent insertions and deletions are required, especially in scenarios where the size of the data isn't known in advance. They're widely used in dynamic memory management, queues, stacks, and even in the implementation of hash tables.
Despite lacking backward traversal (a feature present in doubly linked lists), singly linked lists offer simplicity and efficiency where those constraints are acceptable.

#OUTPUT
