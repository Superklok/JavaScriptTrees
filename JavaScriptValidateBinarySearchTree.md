# JavaScript Validate Binary Search Tree

## Challenge:

Given the `root` of a binary tree, determine if it is a valid binary search tree (BST).

A valid BST is defined as follows:

The left subtree of a node contains only nodes with keys less than the node's key.
<br/>
The right subtree of a node contains only nodes with keys greater than the node's key.
<br/>
Both the left and right subtrees must also be binary search trees.

### 1<sup>st</sup> Example:

`Input: root = [2,1,3]`
<br/>
`Output: true`

### 2<sup>nd</sup> Example:

`Input: root = [5,1,4,null,null,3,6]`
<br/>
`Output: false`
<br/>
`Explanation: The root node's value is 5 but its right child's value is 4.`

### Constraints:

The number of nodes in the tree is in the range `[1, 10⁴]`.
<br/>
`-2³¹ <= Node.val <= 2³¹ - 1`

## Solution:

`const isValidBST = (root, minimum, maximum) => {`
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`if (root == null) return true;`
<br/>
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`if (root.val <= minimum || root.val >= maximum) return false;`
<br/>
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`return isValidBST(root.left, minimum, root.val) && isValidBST(root.right, root.val, maximum);`
<br/>
`};`
<br/>
<br/>