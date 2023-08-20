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
