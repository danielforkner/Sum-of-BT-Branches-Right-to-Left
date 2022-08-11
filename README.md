# Sum-of-BT-Branches-Right-to-Left

## Prompt

Write a function that receives a binary tree and returns an array of the sum of each branch, ordered from rightmost branch to leftmost branch. The sum of a branch is the sum of all node values within that branch.

For example: 

![example Binary Tree](https://github.com/danielforkner/Sum-of-BT-Branches-Right-to-Left/blob/main/example%20tree.png)

The return sumArray should be [ 17, 12, 8, 20, 21 ]
```
// 17 == 1 + 7 + 9
// 12 == 1 + 7 + 4
//  8 == 1 + 2 + 5
// 20 == 1 + 2 + 6 + 11
// 20 == 1 + 2 + 6 + 12
```

## Code Provided

Provide the following code:

```
class BinaryTree {
  constructor(value) {
    this.value = value;
    this.left = null;
    this.right = null;
  }
}

const tree = new BinaryTree(1);
tree.left = new BinaryTree(2);
tree.left.left = new BinaryTree(6);
tree.left.left.left = new BinaryTree(12);
tree.left.left.right = new BinaryTree(11);
tree.left.right = new BinaryTree(5);
tree.right = new BinaryTree(7);
tree.right.left = new BinaryTree(4);
tree.right.right = new BinaryTree(9);

function sumBranches() {
  // your code here
}
```
