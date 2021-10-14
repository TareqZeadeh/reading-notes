# Trees

##### Tree Types to discuss : 
    - Binary tree.
    - Binary search tree.
    - k-ary tree.

#### Terminology :

    - Node : The main component of tree that holds data and reference to next nodes.
    - Root : The first node in the tree.
    - K : Number specifies the maximum number of children node can have.
    - Left : In binary tree, reference to a node.
    - Right : In binary tree a reference to the other node.
    - Edge : The link between parent and child nodes.
    - Leaf : The node that doesn't have children.
    - Height : number of edges to the latest node.


#### Traversals 

- Traversal allows us to travers the trees searching for a node or printing the contents of a tree.
- There are two types of traversals :
    - Depth first.
        - Pre Order : Traverses the root then the left nodes then the right nodes.
            - This approach uses a stack to implement.
            - Keep going to the leaf node and push to the stack until node.left and right is null.
            - pop from the stack and return to the previous node.
            - Traverse the right node in the same sequence.
            - repeat until root.

        - In Order : Traverses the left then the root node then the left nodes.
        - Post Order : Traverses the left then the right nodes then the root node.

    - Breadth first.
        - Traverses through the tree each level node by node.
        - Use a queue in it's implementation.
        - Enqueue the root element.
        - Dequeue the root element and uses it to travers the tree.
        - traverse left and right and enqueue them.
        - Dequeue the left element and uses it for traversing.
        - enqueue the left and right of it.
        - dequeue when reaching the leaf.
        - Repeat until most right element reached.


#### Binary Trees vs K-ary Trees

- Binary trees are restricted to have to children per node.

- K-ary Trees : 
    - A tree that have more than two children node.
    - K is used to define the maximum number of children a node can have.
    - To traverse we use a similar approach to breadth first traversal but we have more node than left and right.
    - Traversing K-ary starts by enqueuing the first node and hence we have one node we can dequeue.
    - Then enqueue all the children of the dequeued node.
    - Then we dequeue the front and traverse using it.
    - Repeat until finished.


#### Binary search trees

- BST have some restrictions other than binary trees which is elements greater than the root are placed on the right side
and smaller will be placed in the left.

- Searching BST can be done quickly since it compares only height times.

- The big O of searching is O(H) which stands for height.