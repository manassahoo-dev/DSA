1. [387. First Unique Character in a String](#387-First-Unique-Character-in-a-String)
2. [First Repeating element](#First-Repeating-element)
3. [Sub Array with zero sum](#Sub-Array-with-zero-sum)
4. [Count Subarray Zero Sum](#Count-Subarray-Zero-Sum)
5. [Common Elements](#Common-Elements)

**Map in Java**

The `Map` interface in Java provides a collection of key-value pairs, where each key is unique and maps to a corresponding value. Here are some popular methods of the `Map` interface in Java:

1. `put(key, value)`: This method adds a new key-value pair to the map or updates the value of an existing key. For example:

```java
Map<String, Integer> map = new HashMap<>();
map.put("apple", 1);
map.put("banana", 2);
map.put("apple", 3); // updates the value of "apple" to 3
```

2. `get(key)`: This method returns the value associated with the specified key, or `null` if the key is not present in the map. For example:

```java
Map<String, Integer> map = new HashMap<>();
map.put("apple", 1);
map.put("banana", 2);
Integer value = map.get("apple"); // returns 1
```

3. `containsKey(key)`: This method returns `true` if the map contains the specified key, or `false` otherwise. For example:

```java
Map<String, Integer> map = new HashMap<>();
map.put("apple", 1);
map.put("banana", 2);
boolean containsKey = map.containsKey("apple"); // returns true
```

4. `keySet()`: This method returns a `Set` view of the keys contained in the map. For example:

```java
Map<String, Integer> map = new HashMap<>();
map.put("apple", 1);
map.put("banana", 2);
Set<String> keys = map.keySet(); // returns ["apple", "banana"]
```

5. `values()`: This method returns a `Collection` view of the values contained in the map. For example:

```java
Map<String, Integer> map = new HashMap<>();
map.put("apple", 1);
map.put("banana", 2);
Collection<Integer> values = map.values(); // returns [1, 2]
```

6. `entrySet()`: This method returns a `Set` view of the key-value pairs contained in the map. For example:

```java
Map<String, Integer> map = new HashMap<>();
map.put("apple", 1);
map.put("banana", 2);
Set<Map.Entry<String, Integer>> entries = map.entrySet(); // returns [{"apple", 1}, {"banana", 2}]
```
**Map in JavaScript**

Here are some popular methods of the `Map` object in JavaScript:

1. `set(key, value)`: This method adds or updates an entry in a `Map` object with a specified key and a value. For example:

```javascript
const myMap = new Map();
myMap.set("bar", "foo");
myMap.set(1, "foobar");
myMap.set("bar", "baz"); // updates the value of "bar" to "baz"
```

2. `get(key)`: This method returns the value associated with the specified key, or `undefined` if the key is not present in the `Map`. For example:

```javascript
const myMap = new Map();
myMap.set("bar", "foo");
myMap.set(1, "foobar");
const value = myMap.get("bar"); // returns "foo"
```

3. `has(key)`: This method returns a boolean indicating whether an element with the specified key exists in the `Map`. For example:

```javascript
const myMap = new Map();
myMap.set("bar", "foo");
myMap.set(1, "foobar");
const hasKey = myMap.has("bar"); // returns true
```

4. `keys()`: This method returns an iterable for the keys of the `Map`. For example:

```javascript
const myMap = new Map();
myMap.set("bar", "foo");
myMap.set(1, "foobar");
const keys = myMap.keys(); // returns an iterable for ["bar", 1]
```

5. `values()`: This method returns an iterable for the values of the `Map`. For example:

```javascript
const myMap = new Map();
myMap.set("bar", "foo");
myMap.set(1, "foobar");
const values = myMap.values(); // returns an iterable for ["foo", "foobar"]
```

6. `entries()`: This method returns an iterable for the key-value pairs of the `Map`. For example:

```javascript
const myMap = new Map();
myMap.set("bar", "foo");
myMap.set(1, "foobar");
const entries = myMap.entries(); // returns an iterable for [["bar", "foo"], [1, "foobar"]]
```

**Here is a table comparing the popular `Map` methods in Java and JavaScript:**

| Method | Java | JavaScript |
| --- | --- | --- |
| Add or update an entry | `put(key, value)` | `set(key, value)` |
| Get the value associated with a key | `get(key)` | `get(key)` |
| Check if a key exists | `containsKey(key)` | `has(key)` |
| Get an iterable for the keys | `keySet()` | `keys()` |
| Get an iterable for the values | `values()` | `values()` |
| Get an iterable for the key-value pairs | `entrySet()` | `entries()` |

## 387. First Unique Character in a String

Given a string s, find the first non-repeating character in it and return its index. If it does not exist, return -1.

```
Example 1:

Input: s = "leetcode"
Output: 0

Example 2:

Input: s = "loveleetcode"
Output: 2

Example 3:

Input: s = "aabb"
Output: -1
```

```js
var firstUniqChar = function(s) {
    const map = new Map();
    
    for(const char of s){
        map.set(char, (map.get(char) || 0 ) + 1);
    }

    for(let i = 0; i < s.length; i++){
        if(map.get(s[i]) === 1){
            return i;
        }
    }
    return -1;
};
```
## First Repeating element

Given an integer array A of size N, find the first repeating element in it.
We need to find the element that occurs more than once and whose index of the first occurrence is the smallest.
If there is no repeating element, return -1.

```
Example 1:

Input A = [10, 5, 3, 4, 3, 5, 6]
Output: 5
Explanation: 5 is the first element that repeats

Example 2:

Input A = [6, 10, 5, 4, 9, 120]
Output: -1
Explanation : There is no repeating element, output -1
```

```java
public int solve(int[] A) {
    int ans = -1;
    Set<Integer> set = new HashSet<Integer>();
    for(int i=A.length-1; i >= 0; i--){
        if(set.contains(A[i])){
            ans = A[i];
        } else {
            set.add(A[i]);
        }
    }
    return ans;
}
```
## Sub Array with zero sum

Given an array of integers A, find and return whether the given array contains a non-empty subarray with a sum equal to 0.
If the given array contains a sub-array with sum zero return 1, else return 0.

```
Example 1:

Input A = [1, 2, 3, 4, 5]
Output: 0
Explanation:  No subarray has sum 0.

Example 2:

Input A = [4, -1, 1]
Output: 1
Explanation :  The subarray [-1, 1] has sum 0.
```
![Screenshot from 2023-06-25 22-41-55](https://github.com/manassahoo-dev/DSA/assets/6974223/25a57a99-f273-4efe-b042-e74f5ac1e651)

```java
public int solve(int[] A) {
    Set<Long> set = new HashSet<Long>();
    long sum = 0;
    set.add(sum);
    for(int a: A){
        sum += a;
        if(set.contains(sum)){
            return 1;
        } else {
            set.add(sum);
        }
    }
    return 0;
}
```    
## Count Subarray Zero Sum

Given an array A of N integers.
Find the count of the subarrays in the array which sums to zero. Since the answer can be very large, return the remainder on dividing the result with 10^9+7

```
Example 1:

Input A = [1, -1, -2, 2]
Output: 3
Explanation: The subarrays with zero sum are [1, -1], [-2, 2] and [1, -1, -2, 2].

Example 2:

Input A = [-1, 2, -1]
Output: 1
Explanation : The subarray with zero sum is [-1, 2, -1].
```
![Screenshot from 2023-06-25 23-00-43](https://github.com/manassahoo-dev/DSA/assets/6974223/2b90f236-bc93-4941-ae23-f41e7cd6276a)

```java
import java.util.HashMap;

public class Solution {
    public int countZeroSumSubarrays(int[] A) {
        int n = A.length;
        long count = 0; // Use long to handle large results
        long sum = 0; // Running sum of the elements
        HashMap<Long, Integer> map = new HashMap<>(); // Store prefix sum frequencies
        
        for (int i = 0; i < n; i++) {
            sum += A[i]; // Add the current element to the sum
            
            if (sum == 0) {
                count++; // If the sum is zero, increment count
            }
            
            if (map.containsKey(sum)) {
                count += map.get(sum); // Add the frequency of the prefix sum to count
                map.put(sum, map.get(sum) + 1); // Increment the frequency
            } else {
                map.put(sum, 1); // Initialize the frequency
            }
        }
        
        int MOD = 1000000007; // Modulo value
        return (int) (count % MOD); // Return the count modulo MOD
    }
}
```    
## Common Elements

Given two integer arrays, A and B of size N and M, respectively. Your task is to find all the **common elements** in both the array.

**NOTE:**

- Each element in the result should appear as many times as it appears in both arrays.
- The result can be in any order.

```
Example 1:

Input  
A = [1, 2, 2, 1]
B = [2, 3, 1, 2]
Output: [1, 2, 2]
Explanation: Elements (1, 2, 2) appears in both the array. Note 2 appears twice in both the array.

Example 2:

Input 
A = [2, 1, 4, 10]
B = [3, 6, 2, 10, 10]
Output: [2, 10]
Explanation : Elements (2, 10) appears in both the array.
```

Approach

- Create a HashMap to store the frequency of elements in array A.
- Iterate through array A and count the frequency of each element in the HashMap.
- Create an ArrayList to store the common elements.
- Iterate through array B.
- Check if the current element exists in the HashMap and has a frequency greater than 0.
    - If it does, add the element to the ArrayList of common elements.
    - Decrement the frequency of the element in the HashMap to account for its occurrence.
- Convert the ArrayList of common elements to an array.
- Return the array containing the common elements.

```java
import java.util.ArrayList;
import java.util.HashMap;
import java.util.List;

public class Solution {
    public int[] findCommonElements(int[] A, int[] B) {
        HashMap<Integer, Integer> mapA = new HashMap<>(); // Store frequency of elements in array A
        
        // Count the frequency of elements in array A
        for (int num : A) {
            mapA.put(num, mapA.getOrDefault(num, 0) + 1);
        }
        
        List<Integer> commonElements = new ArrayList<>(); // Store common elements
        
        // Check each element in array B
        for (int num : B) {
            if (mapA.containsKey(num) && mapA.get(num) > 0) {
                commonElements.add(num); // Add the common element to the list
                mapA.put(num, mapA.get(num) - 1); // Decrement the frequency in array A
            }
        }
        
        int[] result = new int[commonElements.size()]; // Convert list to array
        
        // Copy elements from list to array
        for (int i = 0; i < commonElements.size(); i++) {
            result[i] = commonElements.get(i);
        }
        
        return result;
    }
}
```
