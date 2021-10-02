# Linked Lists :

### Definitios : 
- Is a grou of nodes that are connected to each other , and each node have data and reference that refers to the next node .
- Two types of linked lists : singly , doubly .

### Terminology :

- LinkeList : A data structure that have data and refers to the next node .
- Singly : refers to the number of references the node have the singly refers to the next node .
- doubly : have two references next and previous references .
- Nodes : items and contents of linkedlist that have data and reference lives inside it . 
- Next : refers to the next item in the linked list .
- Head : is the first node in the linked list .
- Current : is the node that I am at .


### Implementation :

- When traversing a linked list we cant use a for or for each loop .
- We use the next reference which will guid us where the next node occurs .
- A good traversing can be implemented using the while loop until the next reference is null .
- if we reached a node that is null A nullReferenceException will be thrown .
- The current will guide us where are we on the node list .
- Traversing : 
    - Create a current node that points to the head to gurantee we are at the starting poin .
    - loop through a while statement until the current is equal to null .
    - inside the loop change the current to the next reference node .
- The big O of time we are using is O (n).
- The big O of space is O(1) hence we don't use additional space .


- Adding a node to the head (O(1)) :
    - Create the node with it's values passed by a parameter .
    - save the reference of the head in a temp .
    - point the newNode to the head .
    - make the head point to the old head .
- Adding a node to the middle : 
    - Traverse through the method until we find the next equals the position we want to add .
    - make the new node points to the next of the current node .
    - now we have two nodes refering to that node .
    - make the current points to the new nodes .
- Printing linked list :
    - can be easily done through traversing the linked list .
    - at each iteration print the node using it's properties or by over riding it's toString method .


## What are Linked Lists :

### Linear data structures :

- Linear data structure is modeling the data sequentially so to reach the last one you have to traverse each element .
- Non - linear data structres are non-sequential data representation .

### Memory management :

- The difference between arrays and linked lists is the way they use memory in our machine .- Arrays use static memory distribution : That means when declared it will allocate memroy side by side int the same place of memory .

- LinkedLists uses dynamic memroy allocation : when created it will alocate memory scattered and might not be in the same place .
- Conclusion that linked list makes memory management more efficent .

### Parts of elements : 

- A linked list consists of nodes which are the elements of it .
- The head which is the starting entry point of the list and each list should have one .
- The list ends with a null reference .
- A node consists of the data it contains and the reference of the next node .

**A node only knows it's data and the reference of the next node it's connected to .**
- Lists are dynamic in the term of size .

### Shapes and sizes : 

Singly Linked List : The simplest type aranges the data in sequential term we can traverse from the beginning to the end . 

Doubly Linked List : Have two references in each node the reference to the next and previous node more dynaymicall traversable .


Circular Linked List : Have a tail node that points to the first node and each nodes is connected with another node even the last node is connected to the first one .


### Big O :

- Is the way to calculate how efficent an algorithm is .
- It's used to determine how effictive an algorithm is in the terms of time and space .
- Big O referes to an order and n refers to number of elements in the algorithm .

### Growing a linked list : 

- Linked lists consists of memory allocations .
- To address an element of linked list we just need to rearrange our pointers .


### When to use list and when not :

- Linked list is a good approach when adding or removing most elements .
- It's slow in searching and finding or modifying elements .
- Linked lists are faster to insert and delete elements .
- Slow to search in a linked list (an array is a better approach in this case ) .
- Have dynamic size to shrink or grow .
- Only allocates memory as required during the runtime .
- Finding an element requires traversal through the linked list .