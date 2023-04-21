## Table of Contents

- [Count of elements](#Count-of-elements)
- [Check if Number is Prime](#check-if-Number-is-Prime)
- [Section 3](#section-3)

- [Contains Duplicate](https://leetcode.com/problems/contains-duplicate/)
- [Missing Number](https://leetcode.com/problems/missing-number/)
- 


**sliding window technique with two pointers**
<table><thead><tr><th>Difficulty</th><th>Problem</th><th>Link</th></tr></thead><tbody><tr><td>Easy</td><td>Maximum Subarray</td><td><a href="https://leetcode.com/problems/maximum-subarray/" target="_new">https://leetcode.com/problems/maximum-subarray/</a></td></tr><tr><td>Easy</td><td>Two Sum II - Input array is sorted</td><td><a href="https://leetcode.com/problems/two-sum-ii-input-array-is-sorted/" target="_new">https://leetcode.com/problems/two-sum-ii-input-array-is-sorted/</a></td></tr><tr><td>Easy</td><td>Squares of a Sorted Array</td><td><a href="https://leetcode.com/problems/squares-of-a-sorted-array/" target="_new">https://leetcode.com/problems/squares-of-a-sorted-array/</a></td></tr><tr><td>Easy</td><td>Valid Palindrome</td><td><a href="https://leetcode.com/problems/valid-palindrome/" target="_new">https://leetcode.com/problems/valid-palindrome/</a></td></tr><tr><td>Easy</td><td>Remove Duplicates from Sorted Array</td><td><a href="https://leetcode.com/problems/remove-duplicates-from-sorted-array/" target="_new">https://leetcode.com/problems/remove-duplicates-from-sorted-array/</a></td></tr><tr><td>Easy</td><td>Reverse Words in a String III</td><td><a href="https://leetcode.com/problems/reverse-words-in-a-string-iii/" target="_new">https://leetcode.com/problems/reverse-words-in-a-string-iii/</a></td></tr><tr><td>Medium</td><td>Minimum Size Subarray Sum</td><td><a href="https://leetcode.com/problems/minimum-size-subarray-sum/" target="_new">https://leetcode.com/problems/minimum-size-subarray-sum/</a></td></tr><tr><td>Medium</td><td>Longest Continuous Increasing Subsequence</td><td><a href="https://leetcode.com/problems/longest-continuous-increasing-subsequence/" target="_new">https://leetcode.com/problems/longest-continuous-increasing-subsequence/</a></td></tr><tr><td>Medium</td><td>Maximum Product Subarray</td><td><a href="https://leetcode.com/problems/maximum-product-subarray/" target="_new">https://leetcode.com/problems/maximum-product-subarray/</a></td></tr><tr><td>Medium</td><td>Find All Anagrams in a String</td><td><a href="https://leetcode.com/problems/find-all-anagrams-in-a-string/" target="_new">https://leetcode.com/problems/find-all-anagrams-in-a-string/</a></td></tr><tr><td>Medium</td><td>Longest Substring Without Repeating Characters</td><td><a href="https://leetcode.com/problems/longest-substring-without-repeating-characters/" target="_new">https://leetcode.com/problems/longest-substring-without-repeating-characters/</a></td></tr><tr><td>Medium</td><td>Minimum Window Substring</td><td><a href="https://leetcode.com/problems/minimum-window-substring/" target="_new">https://leetcode.com/problems/minimum-window-substring/</a></td></tr><tr><td>Hard</td><td>Longest Substring with At Most Two Distinct Characters</td><td><a href="https://leetcode.com/problems/longest-substring-with-at-most-two-distinct-characters/" target="_new">https://leetcode.com/problems/longest-substring-with-at-most-two-distinct-characters/</a></td></tr><tr><td>Hard</td><td>Trapping Rain Water</td><td><a href="https://leetcode.com/problems/trapping-rain-water/" target="_new">https://leetcode.com/problems/trapping-rain-water/</a></td></tr><tr><td>Hard</td><td>Fruit Into Baskets</td><td><a href="https://leetcode.com/problems/fruit-into-baskets/" target="_new">https://leetcode.com/problems/fruit-into-baskets/</a></td></tr><tr><td>Hard</td><td>Longest Repeating Character Replacement</td><td><a href="https://leetcode.com/problems/longest-repeating-character-replacement/" target="_new">https://leetcode.com/problems/longest-repeating-character-replacement/</a></td></tr><tr><td>Hard</td><td>Longest Substring with At Least K Repeating Characters</td><td><a href="https://leetcode.com/problems/longest-substring-with-at-least-k-repeating-characters/" target="_new">https://leetcode.com/problems/longest-substring-with-at-least-k-repeating-characters/</a></td></tr></tbody></table>


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
