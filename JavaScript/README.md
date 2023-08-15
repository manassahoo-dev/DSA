- [33-js-concepts](https://github.com/leonardomso/33-js-concepts)
- [javascript-algorithms](https://github.com/trekhleb/javascript-algorithms)
- [You-Dont-Know-JS](https://github.com/getify/You-Dont-Know-JS)
- [30-seconds-of-code](https://github.com/30-seconds/30-seconds-of-code)
- [awesome-javascript-learning](https://github.com/micromata/awesome-javascript-learning)


- [greatfrontend](https://www.greatfrontend.com/)
- [bigfrontend.dev](https://bigfrontend.dev)

**Best Open-source projects built with Node.js / React.js**

- [IDURAR ERP/CRM](https://github.com/idurar/idurar-erp-crm)
- [cal.com](https://github.com/calcom/cal.com)


- Temporal Dead Zone (TDZ)
- Redux Toolkit


**Flatten an array**

```js
function flatten(array) {
    const flattened = [];
    
    for (const item of array) {
        if (Array.isArray(item)) {
            flattened.push(...flatten(item)); // Recursively flatten nested arrays
        } else {
            flattened.push(item);
        }
    }
    
    return flattened;
}

let array = [1, 2, 3, [4, 5], [6, 7, 8, [9, 10, 11]]];
console.log(flatten(array)); // Output: [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11]
```
