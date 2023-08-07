## Higher Order Function

- In JavaScript, a higher-order function is a function that either takes one or more functions as arguments or returns a function as its result.
- This concept is derived from functional programming and is a powerful feature that allows you to write more modular and reusable code.

**Key aspects of higher-order functions**

1. **Functions as First-Class Citizens:**

In JavaScript, functions are first-class citizens, which means 
- they can be assigned to variables, 
- passed as arguments to other functions, 
- and returned from functions. 
This foundational concept is what enables higher-order functions.

**Accepting Functions as Arguments:**

Higher-order functions can accept other functions as arguments. 
These functions are often referred to as "callbacks" because they are intended to be called back at a later point in time by the higher-order function. 
This allows you to customize the behavior of the higher-order function.

```js
function higherOrderFunction(callback) {
  // Perform some operations
  callback();
}

function callbackFunction() {
  console.log("Callback function called");
}

higherOrderFunction(callbackFunction);

```
