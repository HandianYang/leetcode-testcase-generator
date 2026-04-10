# String

## Description

Generate a string of randomized characters. Each character is randomly selected from the given range and type, such as uppercase and lowercase letters, numbers, and other common symbols. 

## When to use?

+ String
+ Trie

Related topics:
+ [`String`](https://leetcode.com/problem-list/string/)
+ [`Trie`](https://leetcode.com/problem-list/trie/)

## When **NOT** to use

+ String with words seperated by spaces (i.e. **sentence**)
+ **Palindrome**

## How to use

### Parameters

+ `String length` (int): The length of the output string.
+ `type & range` (option & string): The character type that the output string may contain. Each option can be selected by checking the corresponding checkbox, and the range of covered characters can also be specified.
  - `uppercase`: The uppercase letters, ranging from `A` to `Z` (if not specified).
  - `lowercase`: The lowercase letters, ranging from `a` to `z` (if not specified).
  - `number`: The character of digits, ranging from `0` to `9` (if not specified).
  - `other symbol`: Other common symbols to be specified, such as ` `(white space), `.`, `,`. However, you can type letters and digits as well (refer to [Input format](#input-format)).

### Input format

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

The following inputs of `other symbol` are acceptable:

1. Type all covered symbols consecutively.
+ (e.g.) Below specifies that **` `(space), `.`, `/`, and all lowercase letters** are covered. Note that **the duplicated characters will be ignored.** The duplicated characters will not affect the probability of being selected.
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

The following inputs are **UNACCEPTABLE**:

1. Wrong type of characters in range fields.
+ (e.g.) **(WRONG)** `[v] numbers (A-C)`
+ (e.g.) **(WRONG)** `[v] uppercase letters (De)`
2. Wrong usage of dash `-` character.
+ (e.g.) **(WRONG)** `[v] lowercase letters (-)`
+ (e.g.) **(WRONG)** `[v] lowercase letters (--)`
+ (e.g.) **(WRONG)** `[v] lowercase letters (--e)`
3. Irrelevant characters in range fields.
+ (e.g.) **(WRONG)** `[v] lowercase letters (p,q,r)`
+ (e.g.) **(WRONG)** `[v] numbers (1~3)`
+ (e.g.) **(WRONG)** `[v] numbers (7/9)`
4. More than 2 characters (excluded `-`) in range fields.
+ (e.g.) **(WRONG)** `[v] lowercase letters (cdefg)`
+ (e.g.) **(WRONG)** `[v] numbers (1-34)`

### Constraints

1. `String length` should be non-negative.
2. At least one `type` option should be selected.
3. If range(s) are specified, user should input the correct format. Please refer to [Input format](#input-format) for detailed information.