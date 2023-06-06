**Problems**

1. [Elements Removal](#elements-removal)
2. [Noble integers in an array](#noble-integers-in-an-array)
3. [Factors sort](#factors-sort)
4. [Leetcode: 179. Largest Number](#largest-number)
5. [Leetcode: 75. Sort Colors](#sort-colors)
6. [Leetcode: 1502. Can Make Arithmetic Progression From Sequence](#arithmetic-progression)


To sort arrays in JavaScript, you can use the `sort()` method, which sorts the elements of an array **in place** and returns the sorted array. 
By default, the `sort()` method sorts elements as strings. So, to sort numeric arrays correctly, you need to provide a custom comparison function.
```js
const numbers = [4, 2, 7, 1, 9, 5];
const increasingOrder = numbers.sort((a, b) => a - b);
const decreasingOrder = numbers.sort((a, b) => b - a);
```

## Elements Removal

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
## Noble integers in an array

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

## Factors sort

_Problem Description_

Given an array `A` of `N` elements. Sort the given array in increasing order of number of distinct factors of each element, i.e., element having the least number of factors should be the first to be displayed and the number having highest number of factors should be the last one. 
If 2 elements have same number of factors, then number with less value should come first.

**Note**: You cannot use any extra space

_Examples_
```
Input: [6, 8, 9]
Output: [9, 6, 8] (The number 9 has 3 factors, 6 has 4 factors and 8 has 4 factors.)
  
Input: [2, 4, 7]
Output: [2, 7, 4] (The number 2 has 2 factors, 7 has 2 factors and 4 has 3 factors.)
```

**Solution** (Using Custom Sort Comparator)
![Image 1](https://github.com/manassahoo-dev/DSA/assets/6974223/a5dbb4a4-a539-44f0-a600-f65374b7d32a)

```java
public static int getFactors(int a) {
  int factorCounter = 0;
  for (int i = 1; i * i <= a; i++) {
    if (a % i == 0) {
      if (i == a / i) {
        factorCounter++;
      } else {
        factorCounter += 2;
      }
    }
  }
  return factorCounter;
}

public int[] solve(int[] A) {
  Integer[] arr = new Integer[A.length];
  for (int i = 0; i < A.length; i++) {
    arr[i] = A[i];
  }

  Arrays.sort(arr, (a, b) -> {
    int factor_a = getFactors(a);
    int factor_b = getFactors(b);
    if (factor_a == factor_b) return a - b;
    else return factor_a - factor_b;
  });

  for (int i = 0; i < A.length; i++) {
    A[i] = arr[i];
  }

  return A;
}
```

## Largest Number

_Problem Description_

Given a list of non-negative integers `nums`, arrange them such that they form the largest number and return it.
Since the result may be very large, so you need to return a `string` instead of an `integer`.

_Examples_

```
Example 1:

Input: nums = [10,2]
Output: "210"

Example 2:

Input: nums = [3,30,34,5,9]
Output: "9534330"
```

**Solution** (using Custom Comparator)
1. Convert the array of integers to an array of strings.
2. Sort the strings using a custom comparator.
3. In the custom comparator, compare the concatenation of two strings in different orders to determine the sorting order.
```
String order1 = a + b;
String order2 = b + a;
return order2.compareTo(order1);
```
4. Use Arrays.sort to sort the strings in descending order.
5. Handle the special case where all numbers are 0.
6. Concatenate the sorted strings to form the largest number.
7. Return the largest number as a string.

```java
public static String largestNumber(int[] nums) {
  // Convert the array of integers to an array of strings
  String[] numStrings = new String[nums.length];
  for (int i = 0; i < nums.length; i++) {
    numStrings[i] = String.valueOf(nums[i]);
  }

  // Sort the strings using a custom comparator
  Arrays.sort(numStrings, new Comparator < String > () {
    @Override
    public int compare(String a, String b) {
      // Concatenate the strings in different orders and compare them
      String order1 = a + b;
      String order2 = b + a;
      return order2.compareTo(order1); // Compare in reverse order for descending sort
    }
  });

  // Handle the case where all numbers are 0
  if (numStrings[0].equals("0")) {
    return "0";
  }

  // Concatenate the sorted strings to form the largest number
  StringBuilder sb = new StringBuilder();
  for (String numString: numStrings) {
    sb.append(numString);
  }

  return sb.toString();
}
```

## Sort Colors

_Problem Description_

Given an array `nums` with n objects colored red, white, or blue, sort them in-place so that objects of the same color are adjacent, with the colors in the order red, white, and blue.

We will use the integers `0`, `1`, and `2` to represent the color red, white, and blue, respectively.

You must solve this problem without using the library's sort function.

```
Example 1:

Input: nums = [2,0,2,1,1,0]
Output: [0,0,1,1,2,2]

Example 2:

Input: nums = [2,0,1]
Output: [0,1,2]
```

_Approach 1: Counting Sort_

```java
public void sortColors(int[] nums) {
    int[] count = new int[3]; // Array to count the occurrences of each color

    // Count the occurrences of each color
    for (int num : nums) {
        count[num]++;
    }

    int index = 0;

    // Overwrite the original array with the sorted colors
    for (int i = 0; i < count.length; i++) {
        while (count[i] > 0) {
            nums[index++] = i;
            count[i]--;
        }
    }
}
```

_Approach 2: Dutch National Flag Algorithm_

```java
public void sortColors(int[] nums) {
    int low = 0; // Pointer for 0s
    int mid = 0; // Pointer for 1s
    int high = nums.length - 1; // Pointer for 2s

    while (mid <= high) {
        if (nums[mid] == 0) {
            swap(nums, low, mid);
            low++;
            mid++;
        } else if (nums[mid] == 1) {
            mid++;
        } else {
            swap(nums, mid, high);
            high--;
        }
    }
}

private void swap(int[] nums, int i, int j) {
    int temp = nums[i];
    nums[i] = nums[j];
    nums[j] = temp;
}
```
## Arithmetic Progression

_Problem Description_

A sequence of numbers is called an arithmetic progression if the difference between any two consecutive elements is the same.
Given an array of numbers arr, return `true` if the array can be rearranged to form an arithmetic progression. Otherwise, return `false`.

```
Example 1:

Input: arr = [3,5,1]
Output: true
Explanation: We can reorder the elements as [1,3,5] with differences 2, between each consecutive elements.

Example 2:

Input: arr = [1,2,4]
Output: false
Explanation: There is no way to reorder the elements to obtain an arithmetic progression.
```

_Solution_

```java
public boolean canMakeArithmeticProgression(int[] arr) {
    Arrays.sort(arr); // Sort the array in ascending order

    int diff = arr[1] - arr[0]; // Calculate the common difference

    // Check if the remaining elements have the same difference
    for (int i = 2; i < arr.length; i++) {
        if (arr[i] - arr[i - 1] != diff) {
            return false; // If the difference is not the same, it's not an arithmetic progression
        }
    }

    return true; // All elements have the same difference, it's an arithmetic progression
}
```
