# JavaScript Find Bottom Left Tree Value

## Challenge:

Given the `root` of a binary tree, return the leftmost value in the last row of the tree.

### 1<sup>st</sup> Example:

`Input: root = [2,1,3]`
<br/>
`Output: 1`

### 2<sup>nd</sup> Example:

`Input: root = [1,2,3,4,null,5,6,null,null,7]`
<br/>
`Output: 7`

### Constraints:

The number of nodes in the tree is in the range `[1, 10⁴]`.
<br/>
`-2³¹ <= Node.val <= 2³¹ - 1`

## Solution:

`const findBottomLeftValue = (root) => {`
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`if (root === null) return null;`
<br/>
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`const queue = [root];`
<br/>
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`let left = null;`
<br/>
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`while (queue.length) {`
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`const node = queue.shift();`
<br/>
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`if (node.left === null && node.right === null) left = node.val;`
<br/>
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`if (node.right) queue.push(node.right);`
<br/>
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`if (node.left) queue.push(node.left);`
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`}`
<br/>
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`return left;`
<br/>
`};`
<br/>
<br/>