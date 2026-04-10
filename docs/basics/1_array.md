# Numerical Array

## Description

Generate a randomized numerical array in integer type. Each element in the array is randomly selected from a given numerical range.

## When to use

+ 1D numerical array
+ Linked-list
+ Complete binary tree

Related topics:
+ [`Array`](https://leetcode.com/problem-list/array/)
+ [`Linked List`](https://leetcode.com/problem-list/linked-list/)
+ [`Doubly-Linked List`](https://leetcode.com/problem-list/doubly-linked-list/)

## When **NOT** to use

+ 1D **SORTED** array (use `Monotonic numerical array` instead)
+ General binary tree (use `General binary tree` instead)

## How to use

### Parameters

+ `Lower bound` (int): The lower bound of the range. The number can be included in the testcase.
+ `Upper bound` (int): The upper bound of the range. The number can be included in the testcase.
+ `Array length` (int): The length of the output array. 

### Constraints

+ All values should be in INT32 type.
+ `Upper bound` should not be less than `Lower bound`.
+ `Array length` should be non-negative.