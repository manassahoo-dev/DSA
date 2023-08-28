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

const obj = {
    newObj: {
        obj2: {
            obj5: {
                one: 1,
            },
        },
    },
    obj3: {
        obj4: {
            two: 2
        },
    },
};
function flattenObject(ob) {
    const result = {}

    const flatten = (object,parent) => {
        for (let key in object) {
            const value = object[key];
            const updatedKey = parent ? `${parent}.${key}` : key;
            if (typeof value === 'object') {
                flatten(value, updatedKey);
            } else {
                result[updatedKey] = value;
            }
        }
        return result;
    }

    flatten(ob, '');
    return result;
}
console.log(flattenObject(obj));

// Output:
// {
//   'a.b.c': 1,
//   'a.b.d': 2,
//   'a.e': 3,
//   f: 4
// }
```
**Question 2**
create a function that takes an array of file paths, dynamically creates promises for reading those files, and then returns an array containing the content of each file or an error if reading the file fails.

```js
const fs = require('fs');

function readFiles(filePaths) {
  const promises = filePaths.map(filePath => {
    return new Promise((resolve, reject) => {
      fs.readFile(filePath, 'utf8', (err, data) => {
        if (err) {
          reject(err);
        } else {
          resolve(data);
        }
      });
    });
  });

  return Promise.all(promises);
}

const filePaths = ['file1.txt', 'file2.txt', 'file3.txt'];

readFiles(filePaths)
  .then(fileContents => {
    console.log('File contents:', fileContents);
  })
  .catch(errors => {
    console.error('Errors:', errors);
  });
```
