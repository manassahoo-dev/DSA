String Problems
- [912. Sort an Array](#912-Sort-an-Array)
- [151. Reverse Words in a String](#151-Reverse-Words-in-a-String)
- [5. Longest Palindromic Substring](#5-Longest-Palindromic-Substring)
- [14. Longest Common Prefix](#14-Longest-Common-Prefix)
- [67. Add Binary](#67-Add-Binary)
- [242. Valid Anagram](#242-Valid-Anagram)

**Useful Java String methods**

| Method | Description |
| --- | --- |
| `charAt(int index)` | Returns the character at the specified index. |
| `compareTo(String anotherString)` | Compares two strings lexicographically. |
| `concat(String str)` | Concatenates the specified string to the end of this string. |
| `contains(CharSequence s)` | Returns true if and only if this string contains the specified sequence of char values. |
| `endsWith(String suffix)` | Tests if this string ends with the specified suffix. |
| `equals(Object anObject)` | Compares this string to the specified object. |
| `equalsIgnoreCase(String anotherString)` | Compares this String to another String, ignoring case considerations. |
| `indexOf(int ch)` | Returns the index within this string of the first occurrence of the specified character. |
| `lastIndexOf(int ch)` | Returns the index within this string of the last occurrence of the specified character. |
| `length()` | Returns the length of this string. |
| `replace(char oldChar, char newChar)` | Returns a new string resulting from replacing all occurrences of oldChar in this string with newChar. |
| `split(String regex)` | Splits this string around matches of the given regular expression. |
| `startsWith(String prefix)` | Tests if this string starts with the specified prefix. |
| `substring(int beginIndex)` | Returns a new string that is a substring of this string. |
| `toLowerCase()` | Converts all of the characters in this String to lower case using the rules of the default locale. |
| `toUpperCase()` | Converts all of the characters in this String to upper case using the rules of the default locale. |
| `trim()` | Returns a copy of the string, with leading and trailing whitespace omitted. |


```
|--------|------------------|--------------------|
|  Char  | Lowercase Decimal|  Uppercase Decimal |
|--------|------------------|--------------------|
|   a    |        97        |        65          |
|   b    |        98        |        66          |
|   c    |        99        |        67          |
|   d    |        100       |        68          |
|   e    |        101       |        69          |
|   f    |        102       |        70          |
|   g    |        103       |        71          |
|   h    |        104       |        72          |
|   i    |        105       |        73          |
|   j    |        106       |        74          |
|   k    |        107       |        75          |
|   l    |        108       |        76          |
|   m    |        109       |        77          |
|   n    |        110       |        78          |
|   o    |        111       |        79          |
|   p    |        112       |        80          |
|   q    |        113       |        81          |
|   r    |        114       |        82          |
|   s    |        115       |        83          |
|   t    |        116       |        84          |
|   u    |        117       |        85          |
|   v    |        118       |        86          |
|   w    |        119       |        87          |
|   x    |        120       |        88          |
|   y    |        121       |        89          |
|   z    |        122       |        90          |
|--------|------------------|--------------------|
```

**Given a character array toggle every character.**

```
Input: char[] chars = {'H', 'e', 'l', 'L', 'o', '!', 'W', 'o', 'r', 'l', 'D'};
Output: {'h', 'E', 'L', 'l', 'O', '!', 'w', 'O', 'R', 'L', 'd'}
```

```java
public void toggleCharacters(char[] chars) {
    for (int i = 0; i < chars.length; i++) {
        if (chars[i] >= 'A' && chars[i] <= 'Z') {
            // If the character is uppercase, toggle it to lowercase
            chars[i] = (char) (chars[i] + ('a' - 'A'));
        } else if (chars[i] >= 'a' && chars[i] <= 'z') {
            // If the character is lowercase, toggle it to uppercase
            chars[i] = (char) (chars[i] + ('A' - 'a'));
        }
        // Ignore non-alphabetic characters
    }
}
```

**How many ways can we toggle a charcter?**

1. Using the `Character` class methods:
```java
if (Character.isLowerCase(ch)) {
    ch = Character.toUpperCase(ch);
} else if (Character.isUpperCase(ch)) {
    ch = Character.toLowerCase(ch);
}
```
2. Using ASCII manipulation:
```java
if (ch >= 'A' && ch <= 'Z') {
    ch = (char) (ch + ('a' - 'A'));
} else if (ch >= 'a' && ch <= 'z') {
    ch = (char) (ch - ('a' - 'A'));
}
```
3. Using bitwise operations:

```java
ch = (char) (ch ^ 32);
```
```
         A: 0 1 0 0 0 0 0 1
    ^   32: 0 0 1 0 0 0 0 0
    -----------------------
    Result: 0 1 1 0 0 0 0 1 (a)
```

## 912. Sort an Array

Given an array arr. Sort this array using **Count Sort Algorithm** and return the sorted array.

```java
public int[] sort(int[] arr) {
  // Create the counting hash map.
  HashMap < Integer, Integer > counts = new HashMap < > ();
  int minVal = arr[0], maxVal = arr[0];

  // Find the minimum and maximum values in the array,
  // and update it's count in the hash map.
  for (int i = 0; i < arr.length; i++) {
    minVal = Math.min(minVal, arr[i]);
    maxVal = Math.max(maxVal, arr[i]);
    counts.put(arr[i], counts.getOrDefault(arr[i], 0) + 1);
  }

  int index = 0;
  // Place each element in its correct position in the array.
  for (int val = minVal; val <= maxVal; ++val) {
    // Append all 'val's together if they exist.
    while (counts.getOrDefault(val, 0) > 0) {
      arr[index] = val;
      index += 1;
      counts.put(val, counts.get(val) - 1);
    }
  }
  return arr;
}
```

## 151. Reverse Words in a String

Given an input string s, reverse the order of the words.

A word is defined as a sequence of non-space characters. The words in s will be separated by at least one space.

Return a string of the words in reverse order concatenated by a single space.

Note that s may contain **leading or trailing spaces** or **multiple spaces between two words**. The returned string should only have a single space separating the words. Do not include any extra spaces.

```
Example 1:

Input: s = "the sky is blue"
Output: "blue is sky the"

Example 2:

Input: s = "  hello world  "
Output: "world hello"
Explanation: Your reversed string should not contain leading or trailing spaces.

Example 3:

Input: s = "a good   example"
Output: "example good a"
Explanation: You need to reduce multiple spaces between two words to a single space in the reversed string.
``` 

Java Solution
```java
class Solution {
    public static String reverseWords(String s) {
        // Split the input string into an array of words
        String[] words = A.trim().split("\\s+");

        // Reverse the array of words
        StringBuilder reversedString = new StringBuilder();
        for (int i = words.length - 1; i >= 0; i--) {
            reversedString.append(words[i]);
            if (i != 0) {
                reversedString.append(" ");
            }
        }
        return reversedString.toString();
    }    
}
```

JavaScript Solution
```js
function reverseString(A) {
  // Split the input string into an array of words
  const words = A.trim().split(/\s+/);

  // Reverse the array of words
  const reversedWords = [];
  for (let i = words.length - 1; i >= 0; i--) {
    reversedWords.push(words[i]);
  }

  // Join the reversed array of words with a space separator
  const reversedString = reversedWords.join(" ");

  return reversedString;
}
```
## 5. Longest Palindromic Substring
Given a string s, return the longest palindromic substring in s.

```
Example 1:

Input: s = "babad"
Output: "bab"
Explanation: "aba" is also a valid answer.

Example 2:

Input: s = "cbbd"
Output: "bb"
```
Java Solution
```java
class Solution {
    public String longestPalindrome(String s) {
        if (s == null || s.length() < 1) return "";
        int start = 0, end = 0;
        for (int i = 0; i < s.length(); i++) {
            int len1 = expandAroundCenter(s, i, i);
            int len2 = expandAroundCenter(s, i, i + 1);
            int len = Math.max(len1, len2);
            if (len > end - start) {
                start = i - (len - 1) / 2;
                end = i + len / 2;
            }
        }
        return s.substring(start, end + 1);
    }

    private int expandAroundCenter(String s, int L, int R) {
        while (L >= 0 && R < s.length() && s.charAt(L) == s.charAt(R)) {
            L--;
            R++;
        }
        return R - L - 1;
    }
}
```
## 14. Longest Common Prefix
Write a function to find the longest common prefix string amongst an array of strings.

If there is no common prefix, return an empty string "".

 
```
Example 1:

Input: strs = ["flower","flow","flight"]
Output: "fl"

Example 2:

Input: strs = ["dog","racecar","car"]
Output: ""
Explanation: There is no common prefix among the input strings.
```
Java Solution
```java
public String longestCommonPrefix(String[] strs) {
    if (strs == null || strs.length == 0)
        return "";
    
    Arrays.sort(strs);
    String first = strs[0];
    String last = strs[strs.length - 1];
    int c = 0;
    while(c < first.length())
    {
        if (first.charAt(c) == last.charAt(c))
            c++;
        else
            break;
    }
    return c == 0 ? "" : first.substring(0, c);
}
```
## 67. Add Binary

Given two binary strings a and b, return their sum as a binary string.

 
```
Example 1:

Input: a = "11", b = "1"
Output: "100"

Example 2:

Input: a = "1010", b = "1011"
Output: "10101"
```

Java Solution
```java
  public String addBinary(String a, String b) {
    StringBuilder sb = new StringBuilder();
    int carry = 0;
    int i = a.length() - 1;
    int j = b.length() - 1;

    while (i >= 0 || j >= 0 || carry == 1) {
      if(i >= 0)
        carry += a.charAt(i--) - '0';
      if(j >= 0)
        carry += b.charAt(j--) - '0';
      sb.append(carry % 2);
      carry /= 2;
    }
    return sb.reverse().toString();
  }
```  
## 242. Valid Anagram

Given two strings s and t, return true if t is an anagram of s, and false otherwise.

An Anagram is a word or phrase formed by rearranging the letters of a different word or phrase, typically using all the original letters exactly once.

 
```
Example 1:

Input: s = "anagram", t = "nagaram"
Output: true

Example 2:

Input: s = "rat", t = "car"
Output: false
```

Java Solution
```
public boolean isAnagram(String s, String t) {
    int[] alphabet = new int[26];
    for (int i = 0; i < s.length(); i++) alphabet[s.charAt(i) - 'a']++;
    for (int i = 0; i < t.length(); i++) alphabet[t.charAt(i) - 'a']--;
    for (int i : alphabet) if (i != 0) return false;
    return true;
}
```
