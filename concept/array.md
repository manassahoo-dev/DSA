## Table of Contents

- [Count of elements](#Count-of-elements)
- [Check if Number is Prime](#check-if-Number-is-Prime)
- [Section 3](#section-3)

- [Contains Duplicate](https://leetcode.com/problems/contains-duplicate/)
- [Missing Number](https://leetcode.com/problems/missing-number/)
- 


**sliding window technique with two pointers**
1.  [Maximum Subarray](https://leetcode.com/problems/maximum-subarray/)
2.  [Two Sum II - Input array is sorted](https://leetcode.com/problems/two-sum-ii-input-array-is-sorted/)
3.  [Squares of a Sorted Array](https://leetcode.com/problems/squares-of-a-sorted-array/)
4.  [Valid Palindrome](https://leetcode.com/problems/valid-palindrome/)
5.  [Remove Duplicates from Sorted Array](https://leetcode.com/problems/remove-duplicates-from-sorted-array/)
6.  [Reverse Words in a String III](https://leetcode.com/problems/reverse-words-in-a-string-iii/)
7.  [Minimum Size Subarray Sum](https://leetcode.com/problems/minimum-size-subarray-sum/)
8.  [Longest Continuous Increasing Subsequence](https://leetcode.com/problems/longest-continuous-increasing-subsequence/)
9.  [Maximum Product Subarray](https://leetcode.com/problems/maximum-product-subarray/)
10.  [Find All Anagrams in a String](https://leetcode.com/problems/find-all-anagrams-in-a-string/)

### Count of elements
Given an array A of N integers. Count the number of elements that have at least 1 elements greater than itself.

**Hint**: 
- Only elements that are equal to the maximum value of the array do not satisfy this
- Count total number of max element and subtract from the list size to get the answer.
```java
public int solve(ArrayList<Integer> A) {
    Integer max = 0;
    int count = 0;
    for(Integer i: A){
        if(i > max){
            max = i;
            count = 1;
        }else if(i == max){
            count += 1;
        }
    }
    return A.size() - count;
}
```    





Carry Forward Technique






































**Prefix Sum**

Prefix sum is the technique where you precompute & store the cumulative sum of the sequence of elements that allows fast sum calculation of any continuous range.

Let's say we have a sequence of elements A as mentioned below
A = {a0, a1, a2, a3, a4, a5}

so Prefix Sum P will be calculated as
P = {p0, p1, p2, p3, p4, p5}

``` 
where-
p0 = a0
p1 = a1 + a0
p2 = a0 + a1 + a2
p3 = a0 + a1 + a2 + a3 
p4 = a0 + a1 + a2 + a3 + a4
p5 = a0 + a1 + a2 + a3 + a4 + a5


Q) Say we need to sum get sum of all elements from indices 
[2 to 5] => [a2 + a3 + a4 + a5]		or	[p5 - p1] 
[1 to 4] => [a1 + a2 + a3 + a4] 	or	[p4 - p1]
[0 to 4] => [a0 + a1 + a2 + a3 + a4] 	or 	[p4]
```
- **Prefix Sum Formula**
- **Range Sum Query**
- **In-place Prefix Sum**


Suffix Sum
Contribution Technique

| Problem      | Leetcode |
| ----------- | ----------- |
| Set Matrix Zeroes      | [Title](https://leetcode.com/problems/set-matrix-zeroes/)       |
| Paragraph   | Text        |
