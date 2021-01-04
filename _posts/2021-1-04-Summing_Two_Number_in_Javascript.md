---
title: "[JS]Summing Two Number"
date: 2021-01-04 12:47:10

categories:
  - Javascript
---

Here is an array containg numbers. We are going to sum of all possible combinations of two numbers in the array. Simply, we can use nested loops for summing.

```js
var numbers = [3, 9, 4, 12, 7];

for (var i = 0; i < numbers.length; i++) {
  for (var j = i + 1; j < numbers.length; j++) {
    temp.push(numbers[i] + numbers[j]); // temp = [12, 7, 15, 10, 13, 21, 16, 16, 11, 19]
  }
}
```

The next step is to remove duplicates. You may can use `filter()` or `Set()`.

```js
// filter()
answer = temp.filter((el, index) => temp.indexOf(el) === index);

// Set()
answer = [...new Set(temp)];
```

If you want to sort the array `temp`, you can use `sort()`. But `sort()` is for lexicographical order. So, we need to write it this way:

```js
answer.sort((a, b) => a - b);
```

You can find more information about `sort()` [here](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/sort)

Finally, we've got the result

```js
[7, 10, 11, 12, 13, 15, 16, 19, 21]
```
