# Tree
After you read this article [click_here]()to test your information

### Common Terminology
* Node - A Tree node is a component which may contain it’s own values, and references to other nodes

* Root - The root is the node at the beginning of the tree

* K - A number that specifies the maximum number of children any node may have in a k-ary tree. In a binary tree, k = 2.

* Left - A reference to one child node, in a binary tree

* Right - A reference to the other child node, in a binary tree

* Edge - The edge in a tree is the link between a parent and child node

* Leaf - A leaf is a node that does not have any children

* Height - The height of a tree is the number of edges from the root to the furthest leaf

### Sample Tree
![](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/images/BinaryTree1.PNG)

## Traversals
An important aspect of trees is how to traverse them. Traversing a tree allows us to search for a node

* There are two categories of traversals when it comes to trees:

1. Depth First
2. Breadth First

## Depth First
Depth first traversal is where we prioritize going through the depth (height) of the tree first. There are multiple ways to carry out depth first traversal, and each method changes the order in which we search/print the root

![](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/images/tree-example.png)

```
our traversals would result in different paths based in previous digrams:

Pre-order: A, B, D, E, C, F
In-order: D, B, E, A, F, C
Post-order: D, E, B, F, C, A
```
## Pre-order
Pre-order means that the root has to be looked at first. 
![](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/images/DepthTraversal1.PNG)

## Traversal Pseudocode
Here is the pseudocode for all three of the depth first traversals:
```
 Pre-order
ALGORITHM preOrder(root)
// INPUT <-- root node
// OUTPUT <-- pre-order output of tree node's values

    OUTPUT <-- root.value

    if root.left is not Null
        preOrder(root.left)

    if root.right is not NULL
        preOrder(root.right)
        ```
     ```
        
    In-order
    ALGORITHM inOrder(root)
    // INPUT <-- root node
    // OUTPUT <-- in-order output of tree node's values

        if root.left is not NULL
            inOrder(root.left)

        OUTPUT <-- root.value

        if root.right is not NULL
            inOrder(root.right)
     ```   
     ```
Post-order
ALGORITHM postOrder(root)
// INPUT <-- root node
// OUTPUT <-- post-order output of tree node's values

    if root.left is not NULL
        postOrder(root.left)

    if root.right is not NULL
        postOrder(root.right)

    OUTPUT <-- root.value

```

## Breadth First
Breadth first traversal iterates through the tree by going through each level of the tree node-by-node. So, given our starting tree one more time:
![](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/images/tree-example.png)

```
Our output using breadth first traversal is now:

Output: A, B, C, D, E, F
```

# Binary Tree Vs K-ary Trees

![](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/images/BinaryTree2.PNG)

Binary Tree. Trees can have any number of children per node, 

but Binary Trees restrict the number of children to two (hence our left and right children).

## K-ary Trees

If Nodes are able have more than 2 child nodes, we call the tree that contains them a K-ary Tree. In this type of tree we use K to refer to the maximum number of children that each Node is able to have.

#### Breadth First Traversal
![](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/images/KaryTree1.png)

Breadth First Search (BFS) algorithm traverses a graph in a breadthward motion and uses a queue to remember to get the next vertex to start a search, when a dead end occurs in any iteration.

```
this tree Breadth First we should see the output:

Output: A, B, C, D, E, F, G, H
```

