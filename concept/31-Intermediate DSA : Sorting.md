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
![Demo - Page 1](https://github.com/manassahoo-dev/DSA/assets/6974223/7ffbd23c-342d-42c0-b1ba-b2f7c9cec0c4)

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
**Q2. Noble integers in an array**

_Problem Description_

Given an array **A**, find a Noble integer in it. An integer x is said to be Noble in **A** if the number of integers greater than x is equal to x. If there are many Noble integers, return any of them. If there is no, then return -1.

_Examples_
```
Input  : [7, 3, 16, 10]
Output : 3  
Number of integers greater than 3 is three.

Input  : [-1, -9, -2, -78, 0]
Output : 0
Number of integers greater than 0 is zero.
```
![Image 1](https://github.com/manassahoo-dev/DSA/assets/6974223/7d86dea3-69e0-4d7e-ad12-138239b5501d)

**_Brute Force Solution_**

Iterate through the array. For every element `A[i]`, find the number of elements greater than `A[i]`.
```java
public int nobleInteger(int arr[]) {
  int size = arr.length;
  for (int i = 0; i < size; i++) {
    int count = 0;
    for (int j = 0; j < size; j++) {
      if (arr[i] < arr[j])
        count++;
    }

    // If count of greater elements is equal to arr[i]
    if (count == arr[i])
      return arr[i];
  }
  return -1;
}
```
```
Time Complexity: O(n*n) (Two nested for loops)
Space Complexity: O(1) (no extra space has been taken)
```

**_Optimised Solution_** (Use Sorting)
1. Sort the Array arr[] in ascending order. This step takes `(O(nlogn))`.
2. Iterate through the array. Compare the value of index i to the number of elements after index i. 
If arr[i] equals the number of elements after arr[i], it is a noble Integer. 
Condition to check: (`A[i] == length-i-1`). This step takes `O(n)`.

**Note:** Array may have duplicate elements. So, we should skip the elements (adjacent elements in the sorted array) that are same.  

```java
public static int nobleInteger(int arr[]) {
  Arrays.sort(arr);

  // Return a Noble element if present before last.
  int n = arr.length;
  for (int i = 0; i < n - 1; i++) {
    if (arr[i] == arr[i + 1])
      continue;

    // In case of duplicates, we reach last occurrence here.
    if (arr[i] == n - i - 1)
      return arr[i];
  }

  if (arr[n - 1] == 0)
    return arr[n - 1];

  return -1;
}
```
