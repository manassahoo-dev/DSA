## Bitwise Operations
- [Missing Number](https://leetcode.com/problems/missing-number)
- [Bitwise ORs of Subarrays](https://leetcode.com/problems/bitwise-ors-of-subarrays)
 - [XOR Queries of a Subarray](https://leetcode.com/problems/xor-queries-of-a-subarray)
 - [Minimum Flips to Make a OR b Equal to c](https://leetcode.com/problems/minimum-flips-to-make-a-or-b-equal-to-c)
 - [Count Triplets That Can Form Two Arrays of Equal XOR](https://leetcode.com/problems/count-triplets-that-can-form-two-arrays-of-equal-xor/)
 - [Bitwise AND of Numbers Range](https://leetcode.com/problems/bitwise-and-of-numbers-range)
- [Decode XORed Permutation](https://leetcode.com/problems/decode-xored-permutation)

1. Setting a bit: Use the OR operator (|) with a bitmask where the corresponding bit is set to 1.
2. Clearing a bit: Use the AND operator (&) with a bitmask where the corresponding bit is set to 0.
3. Flipping a bit: Use the XOR operator (^) with a bitmask where the corresponding bit is set to 1.
4. Checking if a bit is set: Use the AND operator (&) with a bitmask where only the corresponding bit is set, then check if the result is non-zero.
