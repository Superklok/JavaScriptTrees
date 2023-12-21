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

## Explanation:

I've written a function called `sumOfLeftLeaves` that calculates the sum of the values of the left leaves in a binary tree.
<br/>

If the root node is null, indicating an empty tree, the function immediately returns `0`.
<br/>

If the root node is not null, the function uses destructuring assignment to extract the `left` and `right` children of the root node.
<br/>

The function then recursively calls itself on the "left" and "right" children, storing the returned values in the variables `sumLeft` and `sumRight` respectively.
<br/>

Next, it checks if `sumLeft` is `0`, which means there are no left leaves encountered yet. It also checks if the `left` child exists and is a leaf node, meaning it has no left or right child. If these conditions are met, the value of the leaf node is assigned to `sumLeft`.
<br/>

Finally, the function returns the sum of `sumLeft` and `sumRight`, after converting them to numbers using the "Number" function.
<br/>

In summary, this function recursively calculates the sum of the values of the left leaves in a binary tree. It traverses the tree, keeping track of the sum of the left leaves encountered so far, and returns the final sum.
<br/>
<br/>