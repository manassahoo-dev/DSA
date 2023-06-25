1. [387. First Unique Character in a String](#387-First-Unique-Character-in-a-String)
2. [First Repeating element](#First-Repeating-element)
3. [Sub Array with zero sum](#Sub-Array-with-zero-sum)

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
