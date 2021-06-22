# Trees
In this tutorial, we’ll be covering Binary Trees, Binary Search Trees, and K-ary Trees. We will review some common terminology that is shared amongst all of the trees and then dive into specifics of the different types.

### Sample Tree
![0](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/images/BinaryTree1.PNG)

## Traversals
An important aspect of trees is how to traverse them. Traversing a tree allows us to search for a node, print out the contents of a tree, and much more! There are two categories of traversals when it comes to trees:
* Depth First
* Breadth First

## Depth First
Depth first traversal is where we prioritize going through the depth (height) of the tree first. There are multiple ways to carry out depth first traversal, and each method changes the order in which we search/print the root. Here are three methods for depth first traversal:

* Pre-order: root >> left >> right
* In-order: left >> root >> right
* Post-order: left >> right >> root

![1](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/images/tree-example.png)

* Pre-order: A, B, D, E, C, F
* In-order: D, B, E, A, F, C
* Post-order: D, E, B, F, C, A

The most common way to traverse through a tree is to use recursion. With these traversals, we rely on the call stack to navigate back up the tree when we have reached the end of a sub-path.

## Pre-order
Pre-order means that the root has to be looked at first. In our case, looking at the root just means that we output its value. When we call preOrder for the first time, the root will be added to the call stack:

![2](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/images/DepthTraversal1.PNG)

This means that we will output the root.value out to the console. Then, our next block of code instructs us to check if our root has a left node set. If the root does, we will then send the left node to our preOrder method recursively. This means that we make another function call, where B is our new root:

![3](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/images/DepthTraversal2.PNG)

This process continues until we reach a leaf node. Here’s the state of our tree when we hit our first leaf, D:

![4](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/images/DepthTraversal3.PNG)

It’s important to note a few things that are about to happen:

* The program will look for both a root.left and a root.right. Both will return null, so it will end the execution of that method call
* D will pop off of the call stack and the root will be reassigned back to B
This is the heart of recursion: when we complete a function call, we pop it off the stack and are able to continue execution through the previous function call

![5](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/images/DepthTraversal4.PNG)

The code block will now pick up where it left off when B was the root. Since it already looked for root.left, it will now look for root.right

![6](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/images/DepthTraversal5.PNG)

E will output to the console. Since E is a leaf, it will complete the method code block, and pop E off of the call stack and make its way back up to B.

![7](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/images/DepthTraversal6.PNG)

In the function call, B has already checked for root.left, and root.right. There are no further lines of code to execute, so B will be popped off the call stack, so that we can resume execution of A.

![8](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/images/DepthTraversal7.PNG)

Following the same pattern as we did with the other nodes, A’s call stack frame will pick up where it left off, and check out root.right. C will be added to the call stack frame, and it will the new function’s root

![9](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/images/DepthTraversal8.PNG)

C will be outputted to the console, and root.left will be evaluated. Because C has a left child, preOrder will be called, with the parameter root.left

![10](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/images/DepthTraversal9.PNG)

At this point, the program will find that F does not have any children and it will make its way back up the call stack up to C

![11](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/images/DepthTraversal10.PNG)

C does not have a root.right, so it will pop off the call stack and return to A.

![12](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/images/DepthTraversal11.PNG)

