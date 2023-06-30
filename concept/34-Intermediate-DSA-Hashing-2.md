1. [Longest Subarray Zero Sum](#Longest-Subarray-Zero-Sum)
2. [Check Pair Sum](#Check-Pair-Sum)


## Longest Subarray Zero Sum

Given an array A of N integers. Find the length of the **longest subarray in the array which sums to zero.**


## Check Pair Sum

Given an Array of integers B, and a target sum A.
Check if there exists a pair `(i,j)` such that `Bi + Bj = A and i!=j`.


```
Input Format
First argument A is the Target sum, and second argument is the array B
```
```
Output Format
Return an integer value 1 if there exists such pair, else return 0.
```

```
Input 1:

A = 8   
B = [3, 5, 1, 2, 1, 2]
Output: 1
Explanation: It is possible to obtain sum 8 using 3 and 5.

Input 2:

A = 21   
B = [9, 10, 7, 10, 9, 1, 5, 1, 5]
Output: 0
Explanation: There is no such pair exists.
```

Here are a few common ways to solve it:

1. Brute Force Approach:
   - Use nested loops to iterate through each pair of elements in the array.
   - Check if the sum of the pair equals the target sum.
   - Return 1 if a pair is found; otherwise, return 0.
   - The time complexity of this approach is O(N^2), where N is the length of the array.

2. Two-Pointers Approach:
   - Sort the array in ascending order.
   - Initialize two pointers, one at the start (left) and the other at the end (right) of the sorted array.
   - Compare the sum of the elements at the two pointers with the target sum:
     - If the sum is equal to the target sum, return 1.
     - If the sum is greater than the target sum, decrement the right pointer.
     - If the sum is less than the target sum, increment the left pointer.
   - Repeat the above steps until the pointers meet or cross each other.
   - Return 0 if no pair is found.
   - The time complexity of this approach is O(N log N) due to the sorting step.

3. Hashing Approach:
   - Initialize an empty hash set.
   - Iterate through each element in the array.
   - Calculate the difference between the target sum and the current element.
   - Check if the difference exists in the hash set:
     - If yes, return 1 (pair found).
     - If not, add the current element to the hash set.
   - Return 0 if no pair is found.
   - The time complexity of this approach is O(N), where N is the length of the array.
