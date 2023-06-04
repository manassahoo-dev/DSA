To sort arrays in JavaScript, you can use the `sort()` method, which sorts the elements of an array **in place** and returns the sorted array. 
By default, the `sort()` method sorts elements as strings. So, to sort numeric arrays correctly, you need to provide a custom comparison function.
```js
const numbers = [4, 2, 7, 1, 9, 5];
const increasingOrder = numbers.sort((a, b) => a - b);
const decreasingOrder = numbers.sort((a, b) => b - a);

console.log(increasingOrder);
```
