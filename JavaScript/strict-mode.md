Strict mode is a feature introduced in `ECMAScript 5 (ES5)` that allows developers to opt-in to a stricter set of rules and restrictions when writing JavaScript code. 
When `'use strict'` is added at the beginning of a script or a function, it activates strict mode for that particular scope.

The primary purpose of strict mode is to address some of the problematic and error-prone aspects of the JavaScript language, promoting safer and more predictable behavior. It helps developers write cleaner and more robust code by throwing errors for common mistakes, disallowing certain language features, and preventing potentially hazardous practices.

Some of the key behaviors enforced by strict mode include:

**1. No Implicit Global Variables:**

In strict mode, variables must be explicitly declared using the var, let, or const keywords. Attempting to assign a value to an undeclared variable will result in an error, preventing accidental global variable creation.

```js
// Without strict mode (implicit global variable)
function withoutStrictMode() {
  x = 10;
  console.log(x); // Output: 10
}
withoutStrictMode();

// With strict mode (error for implicit global variable)
function withStrictMode() {
  'use strict';
  y = 20; // Throws ReferenceError: y is not defined
  console.log(y); // This line will not execute due to the error above
}
withStrictMode();
```

**2. Restricted Use of Reserved Words:**

Strict mode prohibits using certain words reserved for future versions of JavaScript, avoiding potential conflicts when new language features are introduced.

```js
'use strict';

// Using reserved word (error in strict mode)
var let = 5; // Throws SyntaxError: Unexpected strict mode reserved word
```

**3. Preventing 'this' Coercion:** 

In strict mode, the value of 'this' is not automatically coerced to the global object when a function is called without any context. Instead, 'this' remains undefined in such cases, highlighting possible context-related issues.

```js
'use strict';

function showThis() {
  console.log(this);
}

showThis(); // Output: undefined
```

**4. No Duplicate Parameters:** 

Functions in strict mode cannot have duplicate parameter names, eliminating ambiguity and potential errors caused by reusing parameter names.

```js
'use strict';

// Duplicate parameters (error in strict mode)
function sum(a, a, c) { // Throws SyntaxError: Duplicate parameter name not allowed in this context
  return a + a + c;
}
```

**5. Restricted 'eval' and 'arguments' Usage:** 

Strict mode makes 'eval' and 'arguments' behave more securely and predictably, preventing accidental variable leaks and ensuring that 'arguments' does not reflect parameter changes.

```js
'use strict';

// Using 'eval' in strict mode
eval('var x = 5;');
console.log(x); // Throws ReferenceError: x is not defined

// Using 'arguments' in strict mode
function displayArgs() {
  console.log(arguments);
}

displayArgs(1, 2, 3); // Output: Throws ReferenceError: arguments is not defined
```

**6. No Octal Numeric Literals:** 

Numeric literals with a leading zero, which would be interpreted as octal numbers in non-strict mode, are not allowed in strict mode. This reduces confusion and ensures consistent behavior across environments.

```js
'use strict';

// Using octal numeric literal (error in strict mode)
var octalNum = 0755; // Throws SyntaxError: Octal literals are not allowed in strict mode
```

**7. No Deleting Immutable Properties:** 

Deleting properties that are non-configurable (e.g., built-in JavaScript properties) results in an error in strict mode, promoting a safer and more robust codebase.

```js
'use strict';

// Deleting a property in strict mode
var obj = {};
Object.defineProperty(obj, 'readOnly', {
  value: 42,
  writable: false,
  configurable: false
});

delete obj.readOnly; // Throws TypeError: Cannot delete property 'readOnly' of #<Object>
```

Strict mode helps developers catch common mistakes, encourages better coding practices, and prepares code for future JavaScript versions. It is recommended to use strict mode in all modern JavaScript projects to enhance code quality and maintainability.


Certainly! Below are some JavaScript quizzes focused on the use of `"use strict"` in markdown format. Test your knowledge of strict mode in JavaScript:

JavaScript Strict Mode Quiz
---------------------------

1.  What is the purpose of using `"use strict"` in JavaScript?
    
    a) It enforces more strict syntax rules for JavaScript code.
    
    b) It enables new ES6 features in older JavaScript engines.
    
    c) It makes the code run faster by optimizing it.
    
    d) It allows JavaScript to run in a restricted environment.
    
2.  How do you enable strict mode in a JavaScript file?
    
    a) `strict mode;`
    
    b) `"use strict";`
    
    c) `use strict;`
    
    d) `strict: true;`
    
3.  When using strict mode, which of the following statements is true?
    
    a) Variables must be declared with `var` keyword.
    
    b) Automatic type coercion is more lenient.
    
    c) Functions can be declared with duplicate names.
    
    d) Global variables are accessible from nested functions.
    
4.  What happens when a non-strict code file is combined with a strict code file?
    
    a) Both files run in strict mode.
    
    b) Both files run in non-strict mode.
    
    c) An error occurs, and the code doesn't run.
    
    d) The strict mode applies only to the strict code file.
    
5.  In strict mode, what will happen if you attempt to delete a variable declared with `var`?
    
    a) It will throw an error.
    
    b) The variable will be deleted successfully.
    
    c) The behavior is the same as in non-strict mode.
    
    d) It will prompt the user for confirmation.
    
6.  In strict mode, what will happen if you use `eval` to evaluate a string containing a variable declaration?
    
    a) The variable will be created in the global scope.
    
    b) The variable will be created in the local scope.
    
    c) It will throw an error.
    
    d) The `eval` function is not affected by strict mode.
    
7.  Which of the following is NOT a benefit of using strict mode?
    
    a) Improved security by eliminating certain JavaScript vulnerabilities.
    
    b) Better performance due to optimized code execution.
    
    c) Prevention of accidental global variable creation.
    
    d) More meaningful error messages in the console.
    

Quiz Answers
------------

1.  Answer: a) It enforces more strict syntax rules for JavaScript code.
    
2.  Answer: b) `"use strict";`
    
3.  Answer: a) Variables must be declared with `var` keyword.
    
4.  Answer: d) The strict mode applies only to the strict code file.
    
5.  Answer: a) It will throw an error.
    
6.  Answer: c) It will throw an error.
    
7.  Answer: b) Better performance due to optimized code execution.
    

Feel free to test your knowledge and check the answers afterward. Remember that using `"use strict"` in your JavaScript code is generally considered a good practice as it helps catch common programming mistakes and enables a safer and more optimized code execution.
