# javascript

1.Temporal Dead Zone

The temporal dead zone (TDZ) is a specific period in the execution of JavaScript code where variables declared with let and const exist but cannot be accessed or assigned any value. During this phase, accessing or using the variable will result in a ReferenceError .

2.Hoisting

In JavaScript, Hoisting is the default behavior of moving all the declarations at the top of the scope before code execution. Basically, it gives us an advantage that no matter where functions and variables are declared, they are moved to the top of their scope regardless of whether their scope is global or local

3.What is closure in JavaScript? 

A closure is the combination of a function bundled together (enclosed) with references to its surrounding state (the lexical environment). In other words, a closure gives you access to an outer function's scope from an inner function. In JavaScript, closures are created every time a function is created, at function creation time.

4.Lexical scope 

Lexical scope is the ability for a function scope to access variables from the parent scope.

5.Async Await

async and await make promises easier to write
async makes a function return a Promise
await makes a function wait for a Promise

6. Promises

Promises in JavaScript are a way to handle asynchronous operations. They provide a cleaner and more organized syntax for dealing with callbacks and managing the flow of asynchronous code. A promise represents the eventual completion or failure of an asynchronous operation, and it has three states:

Pending: The initial state when the promise is created and neither resolved nor rejected.
Fulfilled (Resolved): The operation completed successfully, and the promise has a resulting value.
Rejected: The operation failed, and the promise has a reason for the failure.
A promise is an object with a then method, which is used to register callbacks to be invoked when the promise is fulfilled. Additionally, a catch method is used to handle errors or rejections.

ex:
// Function that returns a promise

function fetchData() {
  return new Promise((resolve, reject) => {
    // Simulate an asynchronous operation (e.g., fetching data from a server)
    setTimeout(() => {
      const success = true; // Simulating a successful response
      if (success) {
        resolve("Data successfully fetched!");
      } else {
        reject("Error fetching data");
      }
    }, 2000); // Simulating a delay of 2000 milliseconds (2 seconds)
  });
}

// Using the promise
fetchData()
  .then(result => {
    console.log("Success:", result);
  })
  .catch(error => {
    console.error("Error:", error);
  });

7.Try catch

The try-catch statement in JavaScript is used for error handling. It allows developers to define a block of code to be tested for errors while providing a mechanism to handle these errors gracefully, preventing them from causing the entire program to crash.

syntax:
try {
  // Code that may throw an exception or error
} catch (error) {
  // Code to handle the exception or error
} finally {
  // Code that will be executed regardless of whether an exception occurred or not (optional)
}
8.Callbak hell
In JavaScript, callbacks are functions passed as arguments to be executed later, often used in asynchronous operations.
Callback hell (or "pyramid of doom") occurs when you have multiple nested callbacks, making the code difficult to read and maintain.

Ex:
doSomething(function(result) {
  doSomethingElse(result, function(newResult) {
    doYetAnotherThing(newResult, function(finalResult) {
      // ...and so on
    });
  });
});

9.What is JavaScript, and how does it differ from Java?

JavaScript is a high-level, interpreted programming language primarily used for building web applications. It is not related to Java in terms of syntax or design; JavaScript is mainly used for client-side scripting in web browsers.

10.Explain the event loop in JavaScript.

The event loop is the mechanism that allows JavaScript to handle asynchronous operations. It continuously checks the message queue for new events (such as user actions or timer events) and executes associated callback functions.

11.What is a closure in JavaScript?

A closure is a function that retains access to variables from its outer (enclosing) scope even after the outer function has finished execution. It forms a closure around the variables it "closes over."

ex: 
function outerFunction() {

  // Outer function scope
  
  let outerVariable = "I am from outerFunction";

  function innerFunction() {
    // Inner function scope
    
    console.log(outerVariable);
  }

  return innerFunction;
}

// Create a closure by calling outerFunction and assigning the result to a variable
let closureExample = outerFunction();

// Call the closure to access the outerVariable
closureExample(); // Output: I am from outerFunction


12.What is the difference between let, const, and var in JavaScript for variable declaration?

let and const were introduced in ES6. let allows for variable reassignment, while const creates a variable that cannot be reassigned. var is the older way of declaring variables; it has function-level scope and can be hoisted.

13.Explain the concept of hoisting in JavaScript.

Hoisting is a JavaScript behavior where variable and function declarations are moved to the top of their containing scope during the compilation phase. This allows you to use variables and functions before they are declared in the code.

14.What are arrow functions in JavaScript, and how do they differ from regular functions?

Arrow functions are a concise way to write functions in JavaScript. They have a shorter syntax, don't have their own this context (they inherit this from the enclosing scope), and cannot be used as constructors.


15.What is the this keyword in JavaScript?

 In JavaScript, this refers to the current execution context. Its value is determined by how a function is called. In the global context, this refers to the global object (e.g., window in a browser). In a method, it refers to the object the method was called on.

16.Explain the difference between == and === in JavaScript.

== is a loose equality operator, performing type coercion if the operands are of different types. === is a strict equality operator that checks both value and type without coercion.

17.What is the purpose of the async and await keywords in JavaScript?

async is used to declare an asynchronous function, and await is used to wait for the resolution of a promise inside an async function. They make it easier to work with asynchronous code, providing a more synchronous-looking syntax.

18.Explain the concept of promises in JavaScript.

Promises are objects that represent the eventual completion or failure of an asynchronous operation. They have three states: pending, fulfilled, and rejected. Promises provide a cleaner syntax for handling asynchronous code compared to callbacks, helping to avoid callback hell.



