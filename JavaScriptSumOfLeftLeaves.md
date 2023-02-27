# JavaScript Sum of Left Leaves

## Challenge:

Given the `root` of a binary tree, return the sum of all left leaves.

A leaf is a node with no children. A left leaf is a leaf that is the left child of another node.

### 1<sup>st</sup> Example:

`Input: root = [3,9,20,null,null,15,7]`
<br/>
`Output: 24`
<br/>
`Explanation: There are two left leaves in the binary tree, with values 9 and 15 respectively.`

### 2<sup>nd</sup> Example:

`Input: root = [1]`
<br/>
`Output: 0`

### Constraints:

The number of nodes in the tree is in the range `[1, 1000]`.
<br/>
`-1000 <= Node.val <= 1000`

## Solution:

`const sumOfLeftLeaves = (root) => {`
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`if (!root) return 0;`
<br/>
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`const {left, right} = root;`
<br/>
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`let [sumLeft, sumRight] = [sumOfLeftLeaves(left), sumOfLeftLeaves(right)];`
<br/>
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`if (!sumLeft && left && !left.left && !left.right) sumLeft = left.val;`
<br/>
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`return Number(sumLeft) + Number(sumRight);`
<br/>
`};`
<br/>
<br/>