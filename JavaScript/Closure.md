JavaScript closures are an essential concept in understanding the behavior of functions and their access to variables. Simply put, a closure is a function that remembers the variables in its scope even when the function is executed outside that scope.

In JavaScript, functions have access to variables defined in their outer scope. When a function is defined inside another function, it forms a closure. This means that the inner function has access to the variables and parameters of its outer function, even after the outer function has finished executing.

Here's an example to illustrate the concept:
```js
function outerFunction() {
  var outerVariable = 'I am outer';

  function innerFunction() {
    console.log(outerVariable); // Accessing the outer variable
  }

  return innerFunction;
}

var closureFunction = outerFunction(); // Assigning the inner function to a variable
closureFunction(); // Calling the inner function
```
1. What is a closure in JavaScript?
2. Explain the concept of scope chain and how it relates to closures.
3. How are closures created in JavaScript?
4. Why are closures useful in JavaScript programming?
5. What is the relationship between closures and garbage collection in JavaScript?
6. How does a closure maintain access to variables from its outer scope even after the outer function has finished executing?
7. What are some practical use cases of closures in JavaScript?
8. How can closures be used to create private variables and encapsulation?
9. Explain the concept of "function factories" and how closures play a role in creating them.
10. What are the potential memory implications when working with closures?
11. How can closures be used to implement callbacks and asynchronous programming in JavaScript?
12. What are the possible challenges or pitfalls to be aware of when working with closures?
13. How do closures affect variable lifetime and memory management in JavaScript?
14. How can you break a closure in JavaScript?
15. Compare and contrast closures and lexical scoping in JavaScript.


# Episode 10 : Closures in JS

### Important Interview Question

**Closure :** Function bundled together with its lexical environment/scope. //Function along with its lexical scope forms a closure.

```
//Example 1

function x(){
  var a = 7;
  function y(){
    console.log(a);
  }
  y();
}

x();
```
```
//Example 2 - Assigning entire function to a variable

function x(){
  var a = function y(){
    console.log(a);
  };
  
  y();
}

x();
```
```
//Example 3 - Passing an entire function as a parameter inside another function

function x(){
  var a = 7;
  
  y();
}

x(function y(){
    console.log(a);
  });
```
```
//Example 4 - return a function from a function

function x(){
  var a = 7;
  function y(){
    console.log(a);
  }
  return y;
}

x();
```
```
//Example 5 - extension of Example 4

function x(){
  var a = 7;
  function y(){
    console.log(a);
  }
  return y;
}

//console.log(z);
var z = x();
console.log(z);
```
-----------------------
When functions are returned from another fun, they still maintain their lexical
scope.
 ```
 //Example 6
 
function x(){
  var a = 7;
  function y(){
    console.log(a);
  }
  return y; //line 6
}

var z = x(); //line 9
console.log(z);
//....................after 1000 lines of code
z(); //line XXD
```
- When y is returned, not only is the function returned but the entire closure (func. y + its lexical scope) is returned and put inside z. Basically at line 5 not just y function was returned but at line 5 the y function along with the lexical scope of y function was returned. Therefore as lexical scope is returned that is why when z is used somewhere else in program like line XXD, it still remembers var a inside x() //so even though after line 9 evn though x() function or x EC no longer exists in the memory but the y() function still remembers its lexical scope/environment or basically where it came from 
- So even though the x function is lost or no longer accessible after line 9, the y function still has a strong binding with its parent x function. This is because the y function is a closure. A closure is a function that has access to the variables of its enclosing scope, even after the enclosing scope has been closed.
- Closure is a very powerful concept of JS, just because this function remembers things even if they are not in their lexical scope

 ```
 //Example 7 - same just another way of writing Example 6
 
function x(){
  var a = 7;
  return function y(){
    console.log(a);
  }
}

var z = x(); 
console.log(z);
//....................after 1000 lines of code
z(); //line XXD
```
### Corner Cases (JS Closure GOTCHAs)
```
//Example 8

function x(){
  var a = 7;
  function y(){
    console.log(a);
  }
  a = 100;
  return y;
}
//console.log(z);
var z = x();
console.log(z);
z();
```
```
//Example 9

function z() {
  var b = 900; 
  function x(){
    var a = 7;
    function y(){
      //var a = 22;
      console.log(a,b);
      //var a = 22;
    }
    y();
  }
  x();
}
z();
```

### Uses of Closure

- Module Design Pattern,
-  Currying, 
-  Functions like once(fun that can be run only once), 
-  memoize, 
-  maintaining state in async world, 
-  setTimeout, 
-  iterators 
-  and many more...
