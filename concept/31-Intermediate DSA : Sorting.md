To sort arrays in JavaScript, you can use the `sort()` method, which sorts the elements of an array **in place** and returns the sorted array. 
By default, the `sort()` method sorts elements as strings. So, to sort numeric arrays correctly, you need to provide a custom comparison function.
```js
const numbers = [4, 2, 7, 1, 9, 5];
const increasingOrder = numbers.sort((a, b) => a - b);
const decreasingOrder = numbers.sort((a, b) => b - a);
```
**Q1. Elements Removal**

_Problem Description_

Given an integer array **A** of size **N**. You can remove any element from the array in one operation.
The cost of this operation is the **sum of all elements** in the array present before this operation.

Find the **minimum cost** to remove all elements from the array.

_Solution_

1. Sort the array A in non-decreasing order, so that the largest element contributes the minimum.
2. Initialize a variable cost to 0 to keep track of the total cost.
3. Iterate through the sorted array A. For each element A[i], add it to the cost variable by multiplying with the occurance.

```java
public int solve(int[] A) {
  int n = A.length;
  Arrays.sort(A);
  int totalSum = 0;
  for (int i = 0; i < n; i++) {
    totalSum += A[i] * (n - i);
  }
  return totalSum;
}
```
