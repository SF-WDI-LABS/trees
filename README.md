<!--
Creator: Team (Brianna)
Last Edited by: Brianna, Cory
Location: SF
-->

![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png)

# Trees

### Why is this important?
<!-- framing the "why" in big-picture/real world examples -->
*This workshop is important because:*

Trees are a common way of structuring data. They can represent sets of information that are hierarchical in nature, like a file system with directories inside directories. Specialized trees are also used for database indexing (btrees) and spell checking (tries), among many other uses.  They are also easy to work with visually, which makes them a common whiteboarding topic.

### What are the objectives?
<!-- specific/measurable goal for students to achieve -->
*After this workshop, developers will be able to:*

- Explain or illustrate the relationship between graphs, trees, and binary search trees.
- Draw a balanced binary search tree from some given data.
- Use binary search trees in answering interview style challenge questions.

### Where should we be now?
<!-- call out the skills that are prerequisites -->
*Before this workshop, developers should already be able to:*

- Describe the low-level structure of arrays and linked lists.
- Draw a linked list.


## Graphs

In computer science, graphs are collections of **vertices** or **nodes**, which usually store or represent some data, and **edges**, which connect the nodes. Each edge connects two nodes together.  If you think of nodes as airports, edges would be the flight paths between them.  Here are some use cases for graphs:

* graph databases
* relationships among users in a social network
* links between pages on a website
* finding a route between two locations
* planning the order of classes to take based on prerequisites

A sequence of edges is called a "path".

<!--<img src="images/paths.jpg" width="300px">-->

## Trees

<img src="images/tree_terms.jpg" width="300px">

Trees are a special kind of graph with some extra rules about their nodes and edges.
* every tree has a unique, special start node called the "root" node. (We usually draw trees vertically with the "root" node at the top of the tree.)
* each node in a tree can only ever have one "parent". This means there's only ever one direct path from any node to the root of the tree.

Terminology:

* edges in a tree are also referred to as "branches".
* nodes of the tree that do not have any children are called "leaves" because no branches lead away from them.
* The length of the longest path from the root to a leaf is called the tree's "height".
* We use family tree terminology when we talk about trees. The root is the "parent" or "ancestor" of all of the rest of the nodes, all other nodes are its "children", "descendants." Nodes that share the same "parent" can be called "siblings."

Here are a few examples of trees in computing:

* **the DOM tree**
* The file system, where directories contain other directories and/or files. The `/` directory is called the "root" directory because it's the root of the computer's directory tree. Use the command `tree` to view the tree structure of any given directory. (You may need to install this capability with `brew install tree`)
* comment trees (where users can comment on comments)
* data compression algoritm trees (Huffman coding)
* single-elimination tournaments
* parser trees or syntax trees that help a computer interpret human-readable code
* the way calculators compute order of operations  


## Trees to Know for the Job Search

### Balanced Binary Search Trees

Balanced Binary Search Trees (balanced BSTs) are very common in interviews because they store data in a sorted order and because they offer `O(log(n))` runtime for some operations. Balanced binary search trees are trees, binary trees, binary search trees, and balanced trees.    We'll break down those new terms. 

#### Binary Trees

**Each node has at most 2 branches**

The most common types of trees for interviews are "binary trees," which allow each node to have up to 2 children. We say each node can have a "left child" and a "right child."  The left child can be considered the root of a "left subtree", and the right child can be considered the root of a "right subtree".

#### Binary Search Trees

**left is less, right is greater**

Binary search trees add on an extra restriction to binary trees. In each node's left child subtree (if it has one), all nodes will will have keys *less* than the original node's key.  In each node's right child subtree (if it has one), all nodes must have a **greater** key than the original node itself (or equal). Left is less!


<img src="images/bst.jpg" width="300px">


#### Balanced Trees

![image](https://cloud.githubusercontent.com/assets/6520345/19444205/57c29be8-9444-11e6-82f3-c1c7dd1dfa3e.png)

Balanced trees are another basic variant of trees. A "balanced" tree minimizes the height of the tree while still holding all its nodes.  You can tell a tree is balanced if all of the "missing children" (areas where another node could be attached but isn't) are either at the very bottom level of the tree or just one level higher. For binary trees, being balanced means the height is `O(log`<sub>`2`</sub>`(n))` (or just `O(log(n))`), where `n` is the number of nodes in the tree.  

#### And finally... Balanced Binary Search Trees

Balanced binary search trees combine the balanced structure requirement with the node key requirement of binary search trees.  If an interview question asks about a tree, it's probably a balanced binary search tree. Ask your interviewer to clarify, though, whether the tree is balanced and whether it is a binary search tree.

<img src="images/bst_complete.jpg" width="300px">


#### Why Are Binary Search Trees Even a Thing?

Below you'll find a table of speeds of common operations for a few of the data structures we've seen: unsorted arrays, sorted arrays, hashes, and binary search trees. The big O notation in the table shows the amortized worst case run time.


<table>
<tbody>
<tr>
	<th></th>
	<th>Insert</th>
	<th>Delete</th>
	<th>Get ith by index</th>
	<th>Select kth in order of value</th>
	<th>Search</th>
	<th>Find minimum</th>
	<th>Find maximum</th>
</tr>
<tr>
	<td>Unsorted array</td>
	<td><i>O</i>(<i>n</i>)<sup>*</sup></td>
	<td><i>O</i>(<i>n</i>)<sup>*</sup></td>
	<td><a href="/wiki/Constant_time" title="Constant time" class="mw-redirect"><i>O</i>(1)</a></td>
	<td><i>O</i>(<i>n</i>&nbsp;log&nbsp;<i>n</i>)<sup>**</sup></td>
	<td><i>O</i>(<i>n</i>)</td>
	<td><i>O</i>(<i>n</i>)</td>
	<td><i>O</i>(<i>n</i>)</td>
</tr>											
<tr>
	<td>Sorted array</td>
	<td><i>O</i>(<i>n</i>)</td>
	<td><i>O</i>(<i>n</i>)</td>
	<td><i>O</i>(1)</td>
	<td><i>O</i>(1)</td>
	<td><i>O</i>(log&nbsp;<i>n</i>)</td>
	<td><i>O</i>(1)</td>
	<td><i>O</i>(1)</td>
</tr>
<tr>
	<td>Hash</td>
	<td><i>O</i>(1)</td>
	<td><i>O</i>(1)</td>
	<td>N/A</td>
	<td><i>O</i>(<i>n</i>)</td>
	<td><i>O</i>(1)</td>
	<td><i>O</i>(<i>n</i>)</td>
	<td><i>O</i>(<i>n</i>)</td>
</tr>
<tr>
	<td>Binary Search Tree<sup>+</sup></td>
	<td><i>O</i>(<i>height</i>)</td>
	<td><i>O</i>(<i>height</i>)</td>
	<td>N/A</td>
	<td><i>O</i>(<i>n</i>)<sup>++</sup></td>
	<td><i>O</i>(<i>height</i>)</td>
	<td><i>O</i>(<i>height</i>)</td>
	<td><i>O</i>(<i>height</i>)</td>
</tr>
</tbody></table>

<sup>\*</sup> Insertion or deletion at the end of an array is usually implemented to be <i>O</i>(1)  (constant time).    
<sup>\*\*</sup>  Sort and then binary search. A faster <i>O</i>(<i>n</i> + <i>k</i>&nbsp;log&nbsp;<i>n</i>) algorithm exists using the heap data structure, which we haven't talked about yet.  There are also faster sorts if you have information about your input.   
<sup>+</sup> For a <a href="/wiki/Self-balancing_binary_search_tree" title="Self-balancing binary search tree" class="mw-redirect">Self-balancing binary search tree</a>, the height is <i>O</i>(log&nbsp;<i>n</i>). If the tree is not balanced, the height can be up to <i>O</i>(<i>n</i>).   
<sup>++</sup> Can reduce to <i>O</i>(<i>height</i>) by augmenting each node to keep track of the size of its subtree.   



## Tree Strategies for Interviews

* Make sure you know whether a tree you're given is binary, self-balancing, a binary search tree. Or, if you're using a tree, clarify which of these properties you want it to have.   
* Be clear about what each node's key is and what other data is stored in the node.   
* Consider storing extra data about the tree inside each node. For example, if you need to find the kth heighest value in a binary search tree, a classic way to go about it is to have each node store the size of its subtree.

## Vocab Practice


1. Use the diagram below to fill in the following table:

	| Node  | parent | left child | right child |
	| :---- | :-- | :-- | :-- |
	| A |  |   |  |
	| B |  |  |  |
	| C |  |   |   |


  <img src="images/labels.jpg" width="300px">

1. In the same diagram (above), which node is the root?  Which are leaves?


1. Finally, in that same diagram, what is the height of the tree?

  <br><br>

1. Which of the following is a tree? (There may be more than one.)

  <img src="images/which_tree.jpg" width="300px">


1. Which of the following is a balanced tree? (There may be more than one.)

  <img src="images/which_balanced.jpg" width="300px">



1. Which of the following is a binary search tree? (There may be more than one.)

  <img src="images/which_bst.jpg" width="300px">



### Vocab Practice **Solutions**

<details><summary>click to reveal</summary>

1. Use the diagram below to fill in the following table:

	| Node  | parent | left child | right child |
	| :---- | :-- | :-- | :-- |
	| A | *B* | *none*  | *none*  |
	| B | *D* | *A* | *C* |
	| C | *B* |  *none* |  *none* |


  <img src="images/labels.jpg" width="300px">

1. In the same diagram (above), which node is the root?  Which are leaves?

  *D is the root.  A, C, and E are leaves.*

1. Finally, in that same diagram, what is the height of the tree?

  *The height is 2, because the longest path from root to leaf has 2 edges/branches in it.*
  <br><br>

1. Which of the following is a tree? (There may be more than one.)

  <img src="images/which_tree.jpg" width="300px">

  *B, D, E are trees.*

  *A is not a tree because one node has 2 parents.*

  *C is not a tree because there is a cycle (a circular path from one node back to that same node).*

  *F is not a tree because it's 2 trees! This is called a "forest".*


1. Which of the following is a balanced tree? (There may be more than one.)

  <img src="images/which_balanced.jpg" width="300px">

  *B, D, and C are balanced because all of the "missing children" in these trees are either at the bottom level or one level above.*

1. Which of the following is a binary search tree? (There may be more than one.)

  <img src="images/which_bst.jpg" width="300px">

  *Only the tree rooted with 6 is a binary search tree. The others both have nodes in the root's left subtree that are greater than the root node.*

</details>

### Today's Challenges

Today's challenges are set up more like what you might encounter in an actual coding interview. We expect you to work in teams of 2 or 3 and do each problem on the whiteboard or the table.  We'll have a very limited time to work on each problem in class, and we'll go over the problems after.  Please do not look at the solutions or look up solutions to these problems online during the drills this morning.


## Challenges

PLEASE DO NOT CODE UNLESS A CHALLENGE SPECIFICALLY INSTRUCTS YOU TO

### Base Challenges (5 minutes)

Do as many of these challenges as you can in 5 minutes. Don't worry if you don't finish them all.

1. By hand on the whiteboard, create a binary search tree from the following array: [0,1,2,3,4,5,6].


1. A "min heap" is another abstract data structure often thought of as a type of binary tree. It has a few additional restrictions, including one called the "min heap property:" every node's key is less than the keys of its children. What is special about the root of a min heap?  

## Binary Search Tree (15 minutes)

**Get as far in this challenge as you can in 15 minutes.**

Assume for the following challenges that you have a binary search tree data structure. The structure will be recursive, meaning each node is actually represented as a full subtree, an instance of `BinarySearchTree`.

The constructor for a `BinarySearchTree` instance requires that you specify the key for the current node, and it sets the left and right subtrees/nodes to  `None` (or `nil` or `null` depending on what programming language you're using; the "pseudocode" solutions use `None`).

The data structure allows you to do the following:

* given a tree called `my_bst`, access the "root node" with `my_bst`
* given any node, find the left child node/subtree of that node with `.left`
* given any node, find the right child node/subtree of that node with `.right`
* given any node, find its key with `.key`


1. You run a website where users can assign creative names to colors. You store named colors as nodes in a self-balancing binary search tree, where the key of a node is the hex code of its color (for example: `#30af99`, `#c0ffee`). Users shouldn't be able to change the name of a color.  Pseudocode a `has_key` function to check if a particular hex value is already in the tree.  If the key is in the tree, your function should return `true`. If the key is not in the tree, your function should return `false`. Your function should take the tree and the hex color key as arguments.


	Stretch Version: Pseudocode an `insert_if_free` function to check if the color exists *and* insert it if it's not already in the tree. If the key is not in the tree, your function should add it to the tree and return `true` (notice this is the reverse of what `has_key` returns).  If the key is already in the tree, your function should return `false`. Your function should take the tree as one argument and the information about the new color as one or more other arguments.  Don't worry about maintaining the balance of the tree; just insert the new node at any valid location.


1. You follow a favorite literary critic's book ratings very closely.  In particular, you keep a self-balancing binary search tree of all the critic's reviews, where each node's key is the rating given by the critic to that node's book.  Every time the critic publishes a new book review, you add it to the tree. Every time you finish reading your current book, you read the next highest-rated book. As a first step to automating your book selection process, pseudocode a `max` function to find the book in the tree with the highest rating. Your function should take the tree as its argument. (A next step would be to also delete the item, but don't work on that right now.)


### Tree

Assume for the following challenge that you have a recursive tree data structure.

The constructor for a `Tree` instance requires that you specify the key for the current node, and it sets `children` list of the node to an empty array.

The data structure allows you to do the following:

* given a tree called `my_tree`, access the "root node" with `my_tree`
* given any node, find an array containing all its children with `.children`
* given any node, find its key with `.key`

In addition, as a special bonus not always available in trees, you can:   
* given any node, find its parent node with `.parent` (the parent of the root node is `None`)

1. Given the names of two people in a military group, and a tree that represents the military hierarchy, your task is to find the lowest-rank person who commands both of the other people (this excludes the people themselves). If there is no such person, return `None`.  This is often called a  `lowest_common_ancestor` function.
