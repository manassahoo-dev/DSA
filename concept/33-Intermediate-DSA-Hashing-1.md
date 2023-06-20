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
