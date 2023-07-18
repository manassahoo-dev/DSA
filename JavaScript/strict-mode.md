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
