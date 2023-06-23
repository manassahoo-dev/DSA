Here are some JavaScript problems to test your understanding of callback functions:

1. Write a function `multiplyByTwo` that takes an array of numbers and returns a new array with each number multiplied by two. Use a callback function to perform the multiplication.

2. Write a function `filterByLength` that takes an array of strings and a number `n` and returns a new array with only the strings that have a length greater than `n`. Use a callback function to perform the length comparison.

3. Write a function `reduceArray` that takes an array of numbers and returns the sum of all the numbers. Use a callback function to perform the addition.

4. Write a function `findMax` that takes an array of numbers and returns the largest number in the array. Use a callback function to perform the comparison.

Example solution to problem 1:

```javascript
function multiplyByTwo(arr, callback) {
  const result = [];
  for (let i = 0; i < arr.length; i++) {
    result.push(callback(arr[i]));
  }
  return result;
}

const numbers = [1, 2, 3, 4, 5];
const doubledNumbers = multiplyByTwo(numbers, function(num) {
  return num * 2;
});

console.log(doubledNumbers); // [2, 4, 6, 8, 10]
```

This function takes an array `arr` and a callback function `callback`. It iterates over each element of the array and applies the callback function to it, pushing the result to a new array `result`. Finally, it returns the new array.

To use this function, we pass in an array of numbers and a callback function that multiplies each number by two. The resulting array is then logged to the console.
