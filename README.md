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

## Starter Code

Provide the following code:

```
class BinaryTree {
  constructor(value) {
    this.value = value;
    this.left = null;
    this.right = null;
  }
}

const root = new BinaryTree(1);
root.left = new BinaryTree(2);
root.left.left = new BinaryTree(6);
root.left.left.left = new BinaryTree(12);
root.left.left.right = new BinaryTree(11);
root.left.right = new BinaryTree(5);
root.right = new BinaryTree(7);
root.right.left = new BinaryTree(4);
root.right.right = new BinaryTree(9);

// Pass in `root` to the following function and write the logic to sum the branches right to left
function sumBranches() {
  // your code here
}
```

## Solutions

Solution 1, with default values:
```
function sumBranches(root, sumArray = [], currentSum = 0) {
  if (root === null) return;

  currentSum += root.value;
  if (root.left === null && root.right === null) {
    sumArray.push(currentSum);
    return sumArray;
  }
  sumBranches(root.right, sumArray, currentSum);
  sumBranches(root.left, sumArray, currentSum);

  return sumArray;
}
```

Solution 2
```
function sumBranches(root) {
  const sumArray = [];
  sumHelper(root, 0, sumArray);
  return sumArray;
}

function sumHelper(node, currentSum, sumArray) {
  if (node === null) return;
  
  currentSum = currentSum + node.value;
  if (!node.left && !node.right) {
    sumArray.push(currentSum);
    return;
  }
  
  sumHelper(node.right, currentSum, sumArray);
  sumHelper(node.left, currentSum, sumArray);
}
```

## Big O
- O(n) time - the function must visit every node in the binary tree to return the sums
- O(n) space - the function traverses the binary tree in place
