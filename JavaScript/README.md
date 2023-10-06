**Websites**
1. [https://eloquentjavascript.net](https://t.co/Ywsp8tAqyy?amp=1)
2. [http://jsforcats.com](https://t.co/lepGOL1AUe?amp=1)
3. [javascript.info](http://javascript.info) 
4. [learnjavascript.online](https://learnjavascript.online)
5. [learn-js.org](https://www.learn-js.org)
6. [https://devdocs.io/javascript/](https://t.co/J8NrkxXZ90?amp=1) 
7. [https://egghead.io/q/javascript](https://t.co/CoI2laB73Z?amp=1) 
8. [https://freecodecamp.org](https://t.co/1bvyYKHs9h?amp=1) 
9. [codecademy](https://www.codecademy.com/learn/introduction-to-javascript)
10. [learnersbucket.com](https://learnersbucket.com)


- [33-js-concepts](https://github.com/leonardomso/33-js-concepts)
- [javascript-algorithms](https://github.com/trekhleb/javascript-algorithms)
- [You-Dont-Know-JS](https://github.com/getify/You-Dont-Know-JS)
- [30-seconds-of-code](https://github.com/30-seconds/30-seconds-of-code)
- [awesome-javascript-learning](https://github.com/micromata/awesome-javascript-learning)

- [greatfrontend](https://www.greatfrontend.com/)
- [bigfrontend.dev](https://bigfrontend.dev)
- [jscafe.dev](https://jscafe.dev/)

**Best Open-source projects built with Node.js / React.js**

- [IDURAR ERP/CRM](https://github.com/idurar/idurar-erp-crm)
- [cal.com](https://github.com/calcom/cal.com)


Concepts
- Temporal Dead Zone (TDZ)
- Redux Toolkit
- Event Bubbling
- Event Capturing

Promises, async/await
Introduction: callbacks
Promise
Promises chaining
Error handling with promises
Promise API
Promisification
Microtasks
Async/await


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



List of important JavaScript topics to revise before your interview:

1. **Advanced JavaScript Concepts:**
   - Closures and Scope
   - Hoisting
   - Event Loop and Asynchronous Programming
   - Promises, Async/Await
   - Callbacks vs. Promises vs. Async/Await

2. **ES6+ Features:**
   - Arrow functions
   - Destructuring
   - Spread and Rest operators
   - Template literals
   - Classes and inheritance
   - Modules (import/export)

3. **Functional Programming:**
   - Higher-order functions
   - Pure functions
   - Immutability
   - Map, Filter, and Reduce
   - Currying and Partial Application

4. **Design Patterns:**
   - Singleton, Factory, Observer, Decorator, etc.
   - Module pattern and Revealing Module pattern
   - Flux and Redux (for state management)
   - MV* patterns (MVC, MVVM)

5. **Asynchronous Programming:**
   - Handling asynchronous control flow
   - Using callbacks effectively
   - Working with Promises and chaining
   - Error handling in asynchronous code

6. **Scope and Closures:**
   - Lexical scoping
   - Closure use cases and examples
   - Memory management and potential memory leaks

7. **DOM Manipulation and Events:**
   - DOM traversal and manipulation techniques
   - Event handling and event delegation
   - Browser events and their properties

8. **Web APIs:**
   - Fetch API for making network requests
   - localStorage and sessionStorage for client-side storage
   - Geolocation API, WebSockets, Web Workers (basic understanding)

9. **Performance and Optimization:**
   - Minification and Compression
   - Debouncing and Throttling
   - Lazy loading of resources
   - Browser rendering process and repaint/reflow

10. **Security:**
    - Cross-Site Scripting (XSS) prevention
    - Cross-Site Request Forgery (CSRF) prevention
    - Content Security Policy (CSP)
    - Same-Origin Policy and CORS

11. **Testing:**
    - Unit testing with frameworks like Jest or Mocha
    - Integration and End-to-End testing
    - Test-driven development (TDD) principles

12. **Build Tools and Bundlers:**
    - Webpack, Babel, Rollup
    - Task runners like Gulp or Grunt

13. **Memory Management and Performance:**
    - Garbage collection in JavaScript
    - Memory leaks prevention and detection

14. **Debugging and Profiling:**
    - Using browser developer tools effectively
    - Profiling performance bottlenecks

15. **Frameworks and Libraries (if relevant):**
    - React, Angular, or Vue (depending on your expertise)
    - Understanding component lifecycle (for React)

16. **Algorithmic Thinking (if relevant):**
    - Data structures and algorithms
    - Problem-solving using JavaScript

17. **Code Quality:**
    - Code linting and formatting (e.g., ESLint, Prettier)
    - Code reviews and best practices

18. **Version Control:**
    - Git commands and workflows

19. **Coding Patterns and Best Practices:**
    - SOLID principles
    - DRY (Don't Repeat Yourself) principle
    - KISS (Keep It Simple, Stupid) principle

20. **Project Experience:**
    - Be prepared to discuss your past projects, challenges faced, and how you overcame them using JavaScript.
   
```js
console.clear();
// Q1
function Q1() {
  console.log(1);
  new Promise((res, rej) => {
    console.log(2);
    rej();
    console.log(4);
  })
    .then(() => {
      console.log(5);
    })
    .catch((error) => {
      console.log(6);
      // commenting the finally block      
    })
    .then(() => {
      console.log(7);
    }).then(() => {
      console.log(9);
    }).then(() => {
      console.log(10);
    });
  console.log(8);
}
// Q1(); // 1 8 2 6 7 

// Q2
let j = 0;
for (var i = 0; i < 2; i++) {
	var self = this;
  setTimeout((i) => {
    // console.log(i);
  }, 1000);
}
// 2 2

// Q3
function Q3() {
  const a = { a: "a" };
  const b = { b: "b" };
  const c = {};

  c[a] = 1; 
  c[b] = 2;
  

  // console.log(c[a]); {"{ a: "a" }": 1}
}

// Q4
// console.log(true.toString()); "True" / "true"
// console.log(10.toString()); "10"

// const f1 = ( a, ...rest) => console.log(a, rest, b)
// f1(1, 2, 3, 4, 5, 6, 7, 8, 9, 10);

// Q5
const obj = {
  firstName: "Tom",
  getName: function () {
    return this.firstName;
  }
};

/* call/ apply/ bind */
/* obj.getName() */
//obj.getName.call(obj)

const getName = obj.getName;
//getName.call(obj)
// console.log(getName());

// Q6
const res1 = [1, 2, 3].reduce((a, b) => a + b, 1);  // 7
const res2 = [1, 2, 3].reduce((a, b) => a + b);	// 6

// Q7
function sum(a, b) {
  return a + b;
}

const func1 = (func) => (a) => (b) =>  func(a)(b)

let doSum = func1(sum);
// console.log(doSum(1)(2)); // 3
```
