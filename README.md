# wysa_leet_Code_Challenge

## Given the root of a binary tree, determine if it is a valid binary search tree (BST).

## Problem Statement:-
### A valid BST is defined as follows:

The left subtree of a node contains only nodes with keys less than the node's key.
The right subtree of a node contains only nodes with keys greater than the node's key.
Both the left and right subtrees must also be binary search trees.
 

Example 1:

Input: root = [2,1,3]
Output: true
Example 2:


Input: root = [5,1,4,null,null,3,6]
Output: false
Explanation: The root node's value is 5 but its right child's value is 4.
 

Constraints:

The number of nodes in the tree is in the range [1, 104].
-231 <= Node.val <= 231 - 1

## Approach using REACTO framework:-

### 1) Reading:-
Given==> 

left subtree of a node <= node's key.

right subtree of a node >= node's key.

left subtree && right subtree both should follow BST.

### 2(i)Example:- 
Input: root = [2,1,3]

Output: true

Since we know 1<2 (which follows left subtree of a node <= node's key.) 

and 2<3 (which follows right subtree of a node >= node's key.)

Therefore output is true

### 2(ii) Example:- 

Input: root = [2,1,3,4,3,null,null]

Output: false

For first tree ,i.e 2,1,3 ==> Output is true

For subtree to the left,i.e 1,4,3 ==> Output is false, because 4<1(false) && (3>1)true==>false && true ==>false

For subtree to the right,i.e 3,null,null ==> Output is true

Therefore final output= false && true = false

### 3) Approach :-

Check and verify according to the definition of BST.

Use recursion until both left and right subtree nodes pointing to null

### 4)Code :-

var isValidBST = function(root, min=null, max=null) {

    if(!root) return true;
    
    if(min && root.val<=min.val)return false;
    
    if(max && root.val>=max.val)return false;
    
    return isValidBST(root.left,min,root) && isValidBST(root.right,root,max)
    
};

### 5) Testcases:-
All passed.

### 6) Order:-

Time Complexicity:- O(n)

SpaceComplexicity :- O(1)

# Note:- I didn't know about this topic so taken the help from youtube to understand it.


