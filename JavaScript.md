1. Differences between let, const, and var in JavaScript?
<table><thead><tr><th></th><th><code>let</code></th><th><code>const</code></th><th><code>var</code></th></tr></thead><tbody><tr><td>Scope</td><td>Block</td><td>Block</td><td>Function/Global</td></tr><tr><td>Reassignment</td><td>Allowed</td><td>Not allowed</td><td>Allowed</td></tr><tr><td>Declaration</td><td>Required</td><td>Required</td><td>Optional</td></tr><tr><td>Hoisting</td><td>Not hoisted</td><td>Not hoisted</td><td>Hoisted to top of function/global scope</td></tr><tr><td>Temporal Dead Zone (TDZ)</td><td>Yes</td><td>Yes</td><td>No</td></tr><tr><td>Use before declaration</td><td>Throws ReferenceError</td><td>Throws ReferenceError</td><td>Returns <code>undefined</code></td></tr><tr><td>Best practice</td><td>Use when you need to reassign a value</td><td>Use when you don't need to reassign a value</td><td>Use when you need hoisting or legacy code support</td></tr></tbody></table>

<ol>
  <li>What is hoisting in JavaScript?</li><li>How does hoisting work in JavaScript?</li>
  <li>What is the difference between function hoisting and variable hoisting?</li>
  <li>What is the order of execution in JavaScript?</li>
  <li>What happens when a variable is hoisted in JavaScript?</li>
  <li>What happens when a function is hoisted in JavaScript?</li>
  <li>What is the value of a hoisted variable before it is declared?</li>
  <li>Can let and const variables be hoisted in JavaScript?</li>
  <li>How can you avoid hoisting in JavaScript?</li>
  <li>What is the best practice for declaring variables in JavaScript to avoid hoisting issues?</li>
  <li>What are some common hoisting-related bugs in JavaScript?</li>
  <li>How does hoisting relate to scope in JavaScript?</li>
  <li>Can hoisting affect the behavior of closures in JavaScript?</li>
  <li>How does hoisting work in ECMAScript 6 (ES6) with let and const variables?</li>
  <li>How does hoisting work with arrow functions in JavaScript?</li>
</ol>
