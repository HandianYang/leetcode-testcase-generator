# Monotonic Numerical Array

## Description

Generate a randomized numerical array in integer type, with elements **listed in increasing/decreasing order**. Each element in the array is randomly selected from a given numerical range.

## When to use

+ 1D **SORTED** numerical array
+ **SORTED** linked-list

Related topics:
+ [`Sorting`](https://leetcode.com/problem-list/sorting/)
+ [`Array`](https://leetcode.com/problem-list/array/)
+ [`Linked List`](https://leetcode.com/problem-list/linked-list/)
+ [`Doubly-Linked List`](https://leetcode.com/problem-list/doubly-linked-list/)

## How to use

### Parameters

+ `Lower bound` (int): The lower bound of the range. The number can be included in the testcase.
+ `Upper bound` (int): The upper bound of the range. The number can be included in the testcase.
+ `Array length` (int): The length of the output array. 
+ `Monotonic type` (option): The monotonic type of the array, with 4 options `non-decreasing`, `non-increasing`, `strictly increasing`, and `strictly decreasing`.

### Constraints

+ All values should be in INT32 type.
+ `Upper bound` should not be less than `Lower bound`.
+ `Array length` should be non-negative.
+ If `strictly increasing` or `strictly decreasing` is selected as the monotonic type option, `Array length` should not larger than `Upper bound - Lower bound + 1`, which is the number of candidate integers within `[Lower bound, Upper bound]`.