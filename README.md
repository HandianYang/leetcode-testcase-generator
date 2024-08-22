# LeetCode Testcase Generator

A simple program that can quickly generate test data for various data structures in LeetCode format.

## Important note

This repository is still under development! All available features can be checked in `main.html` or [Table of Contents](#table-of-contents) (titles with link).

## How to use

### Download the repository

Choose any method to download this repository:
+ Clone via HTTPS

    ```bash
    git clone ...
    ```

+ Clone via SSH

    ```bash
    git clone ...
    ```

+ Download ZIP

### Start generate your testcases!

1. Open `main.html` in any of your favored browser.
1. Select the tab below the "LeetCode Testcase Generator" title.
2. Enter the corresponding content in each field.
3. Click `Generate` button below the fields.
4. Click `Copy` button to copy the generated test case to clipboard. Note that you can only copy the text if your inputs are valid.

## Table of Contents

+ [Basics](#basics)
  - [One-dimensional array](#one-dimensional-array)
    1. [Numerical array](#1-numerical-array)
    2. [Monotonic numerical array](#2-monotonic-numerical-array)
    3. Character array
    4. String array
  - Two-dimensional array
    1. Numerical matrix
    2. Character matrix
  - [Strings](#strings)
    1. [Normal String](#1-normal-string) 
    2. String with words seperated by spaces
+ Data Structures
  - Tree
    1. Normal binary tree
    2. Balanced binary tree
    3. Binary search tree
  - Graph
    1. Unweighted graph
    2. Weighted graph
+ Others
  - Design problem

## Basics

### One-dimensional array

#### 1. Numerical array

##### Description

Generate a randomized numerical array in integer type. Each element in the array is randomly selected from a given numerical range.

##### When to use?

Problems regarding (but not limited to) ...
+ 1D numerical array ([`Array`](https://leetcode.com/tag/array/))
+ linked-list ([`Linked List`](https://leetcode.com/tag/linked-list/), [`Doubly-Linked List`](https://leetcode.com/tag/doubly-linked-list/))

##### When **NOT** to use?

You should not use this function to generate test cases of ...
+ 1D **SORTED** array (use [Monotonic numerical array](#2-monotonic-numerical-array) instead)
+ binary tree (use "Normal binary tree" or other specific trees instead)

##### Parameters

+ **lower bound (int)**: The lower bound of the range. The number MAY NOT be included in the output array.
+ **upper bound (int)**: The upper bound of the range. The number MAY NOT be included in the output array.
+ **length (int)**: The length of the output array. 

##### Constraints

1. Do not leave blank, or type any non-numerical symbols into any input field.
2. **"length"** must be a non-negative number.
3. **"lower bound"** must not be greater than **"upper bound"**.

<!-- ---------------------------------------------------------------------- -->

#### 2. Monotonic numerical array

##### Description

Generate a randomized numerical array in integer type, with elements **listed in increasing/decreasing order**. Each element in the array is randomly selected from a given numerical range.

##### When to use?

Problems regarding (but not limited to) ...
+ 1D SORTED numerical array ([`Array`](https://leetcode.com/tag/array/), [`Sorting`](https://leetcode.com/tag/sorting/))
+ SORTED linked-list

##### Parameters

+ `lower bound (int)`: The lower bound of the range. The number MAY NOT be included in the output array.
+ `upper bound (int)`: The upper bound of the range. The number MAY NOT be included in the output array.
+ `length (int)`: The length of the output array. 
+ `type (option)`: The monotonic type of the array, with 4 options "non-decreasing", "non-increasing", "strictly increasing", and "strictly decreasing".

##### Constraints

1. Do not leave blank, or type any non-numerical symbols into any input field.
2. **"length"** must be a non-negative number.
3. **"lower bound"** must not be greater than **"upper bound"**.
4. For strictly monotonic series, the length of [lowerbound, upperbound] must not be smaller than the length of the array.

<!-- ---------------------------------------------------------------------- -->

### Two-dimensional array

### Strings

#### 1. Normal string

##### Description

Generate a string of randomized characters. Each character is randomly selected from the given range and type, such as uppercase and lowercase letters, numbers, and other common symbols. 

##### When to use?

Problems regarding (but not limited to) ...
+ string ([`String`](https://leetcode.com/tag/string/))
+ trie ([`Trie`](https://leetcode.com/tag/trie/))

<!-- 
##### When NOT to use?

You should not use this function to generate test cases of ...
+ strings with words seperated by spaces
-->

##### Parameters

+ `length (int)`: The length of the output string.
+ `type (option) & range (string)`: The character type that the output string MAY contain. Each option can be selected by checking the corresponding checkbox, and the range of covered characters can also be specified.
  - `uppercase`: The uppercase letters, ranging from `A` to `Z` (if not specified).
  - `lowercase`: The lowercase letters, ranging from `a` to `z` (if not specified).
  - `number`: The character of digits, ranging from `0` to `9` (if not specified).
  - `other symbol`: Other common symbols to be specified, such as ` `(white space), `.`, `,`. However, you can type letters and digits as well (refer to [Input format](#input-format)).

##### Input format

The following inputs of `range` are acceptable:
1. **Leave blank**: all characters of that type are covered.
+ (e.g.) Below specifies that **all uppercase and lowercase letters** are covered.
  ```
  [v] uppercase letters ()
  [v] lowercase letters ()
  [ ] numbers
  [ ] other symbols
  ```
2. **`X`**: only the character of that type is covered.
+ (e.g.) Below specifies that **`A` and all digits** are covered.
  ```
  [v] uppercase letters (A)
  [ ] lowercase letters
  [v] numbers ()
  [ ] other symbols
  ```
3. **`X-`**/**`-X`**: all characters after/before `X` (inclusive) of that type are covered.
+ (e.g.) Below specifies that **`a-c` and `2-9`** are covered. Note that **the number begins with `0`**, so the input `2-` represents `23456789` rather than `234567890`. Similarly, the input `-3` represents `0123` instead of `123`. 
  ```
  [ ] uppercase letters
  [v] lowercase letters (-c)
  [v] numbers (2-)
  [ ] other symbols
  ```
+ (e.g.) Below specifies that **`A` and `9`** are covered. Here, `-A` is equal to `A`, and `9-` is equal to `9`. 
  ```
  [v] uppercase letters (-A)
  [ ] lowercase letters
  [v] numbers (9-)
  [ ] other symbols
  ```
4. **`X-Y`**/**`XY`** or **`Y-X`**/**`YX`**: all characters from `X` to `Y` (inclusive) are covered. The reversed range is acceptable as well.
+ (e.g.) Below specifies that **`A-E`, `x-z`, and `2-4`** are covered. Here, `4-2` is the same as `2-4`.
  ```
  [v] uppercase letters (A-E)
  [v] lowercase letters (xz) 
  [v] numbers (4-2)
  [ ] other symbols
  ```
+ (e.g.) Below specifies that **`G` and `y`** are covered. Here, `G-G` is the same as `G`, and `yy` is the same as `y`.
  ```
  [v] uppercase letters (G-G)
  [v] lowercase letters (yy) 
  [ ] numbers
  [ ] other symbols
  ```

The following explains the format of `other symbol`:
1. Type all covered symbols consecutively.
+ (e.g.) Below specifies that **` `(space), `.`, `/`, and all lowercase letters** are covered. Note that **the duplicated characters will be ignored.** Specifically, the duplicated characters will not affect the probability of being selected.
  ```
  [ ] uppercase letters
  [v] lowercase letters ()
  [ ] numbers
  [v] other symbols ( .///)
  ```
2. Type letters and/or digits if the desired range of any type is discontinuous.
+ (e.g.) Below specifies that **`A-F`, `I`, `O`, and `U`** are covered. Since `A` and `E` are already specified at the uppercase letters option (`A-F`), they are considered duplicated, and thus should be ignored.
  ```
  [v] uppercase letters (A-F)
  [ ] lowercase letters
  [ ] numbers
  [v] other symbols (AEIOU)
  ```
+ (e.g.) Below specifies that **all odd digits** are covered.
  ```
  [ ] uppercase letters
  [ ] lowercase letters
  [ ] numbers
  [v] other symbols (13579)
  ```

##### Constraints

1. Do not leave blank, or type any non-numerical symbols into the `length` field.
2. `length` must be a non-negative number.
3. Select at least one option of `type`.
4. Do not type characters into mismatch fields.
  + (WRONG) `[v] numbers (A-C)`
  + (WRONG) `[v] uppercase letters (De)`
5. Use `-` carefully and correctly.
  + (WRONG) `[v] lowercase letters (-)`
  + (WRONG) `[v] lowercase letters (--)`
  + (WRONG) `[v] lowercase letters (--e)`
6. Do not type any irrelevant characters, except for `other symbol`.
  + (WRONG) `[v] lowercase letters (p,q,r)`
  + (WRONG) `[v] numbers (1~3)`
  + (WRONG) `[v] numbers (7/9)`
7. Do not type more than two characters (`-` does not count) in `range`, except for `other symbol`.
  + (WRONG) `[v] lowercase letters (cdefg)`
  + (WRONG) `[v] numbers (1-34)`

<!-- ---------------------------------------------------------------------- -->