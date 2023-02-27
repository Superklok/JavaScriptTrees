# JavaScript Same Tree

## Challenge:

Given the roots of two binary trees `p` and `q`, write a function to check if they are the same or not.

Two binary trees are considered the same if they are structurally identical, and the nodes have the same value.

### 1<sup>st</sup> Example:

`Input: p = [1,2,3], q = [1,2,3]`
<br/>
`Output: true`

### 2<sup>nd</sup> Example:

`Input: p = [1,2], q = [1,null,2]`
<br/>
`Output: false`

### 3<sup>rd</sup> Example:

`Input: p = [1,2,1], q = [1,1,2]`
<br/>
`Output: false`

### Constraints:

The number of nodes in both trees is in the range `[0, 100]`.
<br/>
`-10⁴ <= Node.val <= 10⁴`

## Solution:

`const isSameTree = (p, q) => {`
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`return JSON.stringify(p) === JSON.stringify(q);`
<br/>
`};`
<br/>
<br/>