# Pair Sum

## Interviewer Prompt
Given an array of N numbers sorted in ascending order (least to greatest), and a separate number (a "sum"), determine if any 2 numbers in the array add up to the sum. Return true if any 2 different numbers within the array add up to sum. Return false if no 2 numbers in the array add up to sum.


## Examples

```js
pairSum([1, 1, 2, 3, 4, 5], 7) -> true
pairSum([1, 2, 3, 4, 5], 10) -> false
pairSum([0, 2, 3, 6, 9, 10], 10) -> true
pairSum([1, 2, 3, 7, 8], 7) -> false
pairSum([-2, 0, 4, 6, 10], 8) -> true
pairSum([1, 2, 3, 4, 5], 2) -> false
```

_Examples - Edge cases_

```js
pairSum([1], 2) -> false
pairSum([2], 2) -> false
pairSum([], 1) -> false
```

# Brute force

## Approach: __Nested loops__

The easiest way to approach this problem is looping over the given array, fixing element at position `i` and looping over it again, from `i+1` up to element at `N-1` position, adding the fixed element to the current one. If it matches `sum` returns `true`. Otherwise, continue the loop up to the end of the array. If there is no match, return `false`

### Code
```js
function pairSum(arr, sum) {
  for(let i = 0; i < arr.length-1; i++) {
    const fixed = arr[i]
    for(let j = i+1; j < arr.length; j++) {
      const current = arr[j]
      if(fixed + current === sum) {
        return true
      }
    }
  }
  return false
}
```
