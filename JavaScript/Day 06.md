  - Flatten an Object
  - Object creation
  - Inheritance
  - Object descriptors
  - Seal, Freeze
  - Accessor, Mutator
  
**Question 1:**
Flatten an Object
Write a function flattenObject that takes a nested object and returns a flattened version of it. 
The keys in the flattened object should be constructed using dot notation. 
For example:

```js
const obj = {
  a: {
    b: {
      c: 1,
      d: 2,
    },
    e: 3,
  },
  f: 4,
};

console.log(flattenObject(obj));
// Output:
// {
//   'a.b.c': 1,
//   'a.b.d': 2,
//   'a.e': 3,
//   f: 4
// }
```
