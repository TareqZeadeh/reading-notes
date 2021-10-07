# Stack 
## Def. Linear data structure that have a node pointing to the next value and not the previous one .
- Stacks follows these principles : 
    - FILO : First in last out .
    - LIFO : Last in first out .

- Terminology : 

    - Top : is the newest element added to the top of the stack .
    - Push O (1) : Adds an element to the top of stack , using linkedlist will make the current top equals new node and the old top will point to the new top .
    - Pop  O (1) : Removes the top item from the stack and make the top the top.next . 
    - Peek O (1) : Returns the top element of the stack .
    - isEmpty O (1) : Returns boolean true if the stack is empty .


# Queue
## Def. Linear Data structure that have two pointers the front which will be dequeued from and the rear which will add to queue after it .

- Queues follows These principles : 

    - FIFO : First in first out .
    - LILI : Last in last out .


- Terminology : 

    - Front : The front element which is the first element added (The oldest)
    - Rear : The latest element added which will be added after it .
    - enqueue O(1): Add a node to the rear of the queue using a pointer connectiong rear elements.next .
    - dequeue O(1): Removing the front element using the pointer to be front.next.next .
    - peek O(1): Returns the front element of the queue which is the oldest element or first element added .
    - isEmpty O(1): Returns boolean true if the queue is empty .