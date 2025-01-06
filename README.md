# JavaScript Loose Comparison Bug

This repository demonstrates a common error in JavaScript where loose comparison (==) is used instead of strict comparison (===). Loose comparison can lead to unexpected results when comparing values of different types.

## Bug

The `foo` function uses loose comparison (`==`) to check if either `a` or `b` is null. This can lead to unexpected results when comparing values of different types.

For example:

```javascript
console.log(foo(1, null)); // Output: null
console.log(foo(null, 1)); // Output: null
console.log(foo(1, 2)); // Output: 3
```

## Solution

The solution is to use strict comparison (`===`) instead of loose comparison (`==`). Strict comparison only returns true if the values are of the same type and have the same value.

```javascript
function foo(a, b) {
  if (a === null || b === null) {
    return null;
  }
  return a + b; 
}

console.log(foo(1, null)); // Output: null
console.log(foo(null, 1)); // Output: null
console.log(foo(1, 2)); // Output: 3
```