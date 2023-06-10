Useful Java String methods

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
            chars[i] = (char) (chars[i] - ('a' - 'A'));
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

Note that s may contain leading or trailing spaces or multiple spaces between two words. The returned string should only have a single space separating the words. Do not include any extra spaces.

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

```java
class Solution {
    public static String reverseWords(String s) {
        // Remove leading and trailing spaces
        s = s.trim();
        
        // Split the string into words based on one or more spaces
        String[] words = s.split("\\s+");
        
        
        // Reverse the array of words
        reverseArray(words);
        
        // Join the reversed words with a single space separator
        return String.join(" ", words);
    }
    
    public static void reverseArray(String[] arr) {
        int start = 0;
        int end = arr.length - 1;
        
        while (start < end) {
            String temp = arr[start];
            arr[start] = arr[end];
            arr[end] = temp;
            start++;
            end--;
        }
    }
}
```    
