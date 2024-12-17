# JavaScript Bug: Unexpected Behavior with undefined Values

This repository demonstrates a subtle bug in JavaScript related to how functions handle `undefined` values when explicit null checks are implemented.  The issue arises when a function is designed to handle `null` values but fails to account for `undefined` separately, leading to unexpected behavior and potential errors.

## Bug Description
The core problem lies in the `foo` function. While it correctly returns 0 for a `null` input, it returns 1 for an `undefined` input.  This is because JavaScript's loose comparison (`===`) doesn't explicitly distinguish between `null` and `undefined` in certain contexts; in this case, the `else if (x < 0)` block is reached, causing `undefined` to be treated as a positive number.

## Solution
The solution requires explicitly handling the `undefined` case separately to avoid unexpected outputs, and using strict equality for comparison.