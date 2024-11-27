# JavaScript Interview Questions

This repository contains a comprehensive list of **500 JavaScript interview questions**. The questions are organized into various categories to help developers at different levels prepare for technical interviews.

---

## Table of Contents

| Section                            | Description                                                       |
|-------------------------------------|-------------------------------------------------------------------|
| [Introduction](#introduction)       | Overview of the repository and its purpose                        |
| [Questions List](#questions-list)   | List of 157 JavaScript interview questions categorized by topic   |

---

## Introduction

This repository contains **500 JavaScript interview questions** across a wide range of topics, from basic to advanced JavaScript concepts. Whether you're just starting with JavaScript or preparing for an advanced interview, this list will help you strengthen your knowledge and practice common interview problems.

---

## Questions List

### **Basic JavaScript (1-50)**

| No. | Question                                                       | Example/Explanation                                            |
|-----|---------------------------------------------------------------|----------------------------------------------------------------|
| 1   | What are the primitive data types in JavaScript?               | `string`, `number`, `boolean`, `null`, `undefined`, `symbol`, `bigint` |
| 2   | What is the difference between `let`, `const`, and `var` in JavaScript? | `let` is block-scoped, `const` is also block-scoped but cannot be reassigned, `var` is function-scoped. |
| 3   | What is a closure in JavaScript?                               | A closure is a function that retains access to its lexical environment, even after the outer function has executed. <br> **Example:** <br> ```javascript <br> function outer() { <br>     let outerVar = 'I am outer'; <br>     return function inner() { <br>         console.log(outerVar); <br>     }; <br> } <br> const closureExample = outer(); <br> closureExample(); // Outputs: "I am outer" <br> ``` |
| 4   | How does JavaScript handle type coercion?                      | JavaScript automatically converts values between different types in certain situations. This is called **type coercion**. <br> **Example:** <br> ```javascript <br> '5' + 2 // '52' (string concatenation) <br> 5 + '5' // '55' (string concatenation) <br> '5' - 2 // 3 (numeric subtraction) <br> ``` |
| 5   | What is the difference between `null` and `undefined`?         | `null` is an explicit assignment representing "no value," while `undefined` represents an uninitialized or non-existent value. <br> **Example:** <br> ```javascript <br> let a = null; <br> let b; <br> console.log(a); // null <br> console.log(b); // undefined <br> ``` |
| 6   | What is the purpose of the `this` keyword in JavaScript?        | `this` refers to the context in which the function is called. It could refer to an object, the window, or be undefined in strict mode. <br> **Example:** <br> ```javascript <br> const person = { <br>     name: 'John', <br>     greet: function() { <br>         console.log(`Hello, ${this.name}`); <br>     } <br> }; <br> person.greet(); // 'Hello, John' <br> ``` |
| 7   | Explain the concept of hoisting in JavaScript.                 | Hoisting is JavaScript's behavior of moving declarations (but not initializations) to the top of their containing scope. <br> **Example:** <br> ```javascript <br> console.log(a); // undefined <br> var a = 5; <br> console.log(b); // ReferenceError <br> let b = 10; <br> ``` |
| 8   | What are template literals in JavaScript?                      | Template literals allow for multi-line strings and expression interpolation. They are enclosed in backticks (`) and use `${}` for embedding expressions. <br> **Example:** <br> ```javascript <br> const name = 'Alice'; <br> const greeting = `Hello, ${name}!`; <br> console.log(greeting); // 'Hello, Alice!' <br> ``` |
| 9   | What is the difference between `==` and `===` in JavaScript?    | `==` compares values with type coercion, while `===` compares both value and type without type coercion. <br> **Example:** <br> ```javascript <br> 5 == '5'  // true <br> 5 === '5' // false <br> ``` |
| 10  | What is a callback function in JavaScript?                     | A callback function is a function passed into another function as an argument, to be executed later. <br> **Example:** <br> ```javascript <br> function greet(name, callback) { <br>     console.log(`Hello, ${name}`); <br>     callback(); <br> } <br> function sayGoodbye() { <br>     console.log('Goodbye!'); <br> } <br> greet('Alice', sayGoodbye); <br> // Output: "Hello, Alice" "Goodbye!" <br> ``` |
| 11  | How do you create an object in JavaScript?                     | Objects can be created using object literals, `Object()` constructor, or `Object.create()`. <br> **Example:** <br> ```javascript <br> const person = { <br>     name: 'John', <br>     age: 30, <br>     greet: function() { console.log('Hello!'); } <br> }; <br> console.log(person.name); // 'John' <br> ``` |
| 12  | What is event delegation in JavaScript?                        | Event delegation is the practice of using a single event listener to manage events for multiple elements. <br> **Example:** <br> ```javascript <br> document.querySelector('ul').addEventListener('click', function(event) { <br>     if (event.target.tagName === 'LI') { <br>         console.log(`Item clicked: ${event.target.textContent}`); <br>     } <br> }); <br> ``` |
| 13  | What is the purpose of the `bind()` method in JavaScript?      | The `bind()` method creates a new function that, when invoked, has its `this` set to the provided object. <br> **Example:** <br> ```javascript <br> const person = { name: 'John' }; <br> function greet() { <br>     console.log(`Hello, ${this.name}`); <br> } <br> const boundGreet = greet.bind(person); <br> boundGreet(); // "Hello, John" <br> ``` |
| 14  | What is the difference between `call()` and `apply()` in JavaScript? | `call()` and `apply()` are similar; they both set the `this` value and accept arguments. The difference is that `call()` takes arguments as a list, while `apply()` takes them as an array. <br> **Example:** <br> ```javascript <br> function greet(city, country) { <br>     console.log(`Hello, ${this.name} from ${city}, ${country}`); <br> } <br> const person = { name: 'John' }; <br> greet.call(person, 'New York', 'USA'); <br> greet.apply(person, ['New York', 'USA']); <br> ``` |
| 15  | What is the difference between `forEach()` and `map()`?        | `forEach()` iterates over the array and performs a side effect on each item but returns `undefined`, while `map()` transforms each item and returns a new array. <br> **Example:** <br> ```javascript <br> const numbers = [1, 2, 3]; <br> numbers.forEach(num => console.log(num * 2)); // Logs 2, 4, 6 <br> const doubled = numbers.map(num => num * 2); <br> console.log(doubled); // [2, 4, 6] <br> ``` |
| 16  | How does the `Array.prototype.filter()` method work?           | `filter()` creates a new array with all elements that pass the test implemented by the provided function. <br> **Example:** <br> ```javascript <br> const numbers = [1, 2, 3, 4, 5]; <br> const evenNumbers = numbers.filter(num => num % 2 === 0); <br> console.log(evenNumbers); // [2, 4] <br> ``` |
| 17  | What is the purpose of the `slice()` method in JavaScript?     | `slice()` returns a shallow copy of a portion of an array into a new array object. <br> **Example:** <br> ```javascript <br> const arr = [1, 2, 3, 4, 5]; <br> const sliced = arr.slice(1, 4); <br> console.log(sliced); // [2, 3, 4] <br

> ``` |
| 18  | How do you check if an array contains a specific element?     | You can use the `includes()` method to check if an array contains a specific element. <br> **Example:** <br> ```javascript <br> const arr = [1, 2, 3]; <br> console.log(arr.includes(2)); // true <br> console.log(arr.includes(5)); // false <br> ``` |
| 19  | What is a JavaScript promise?                                  | A promise is an object that represents the eventual completion (or failure) of an asynchronous operation and its resulting value. <br> **Example:** <br> ```javascript <br> const myPromise = new Promise((resolve, reject) => { <br>     const success = true; <br>     if (success) { <br>         resolve('Success!'); <br>     } else { <br>         reject('Failure'); <br>     } <br> }); <br> myPromise.then(result => console.log(result)).catch(error => console.log(error)); <br> ``` |
| 20  | What is `async` and `await` in JavaScript?                     | `async` makes a function return a promise, and `await` pauses the execution of the async function until the promise is resolved. <br> **Example:** <br> ```javascript <br> async function fetchData() { <br>     let response = await fetch('https://api.example.com/data'); <br>     let data = await response.json(); <br>     console.log(data); <br> } <br> fetchData(); <br> ``` |

---

### **Intermediate JavaScript (51-150)**

| No. | Question                                                       | Example/Explanation                                            |
|-----|---------------------------------------------------------------|----------------------------------------------------------------|
| 51  | What is the `map()` method in JavaScript?                      | `map()` creates a new array populated with the results of calling a provided function on every element in the array. <br> **Example:** <br> ```javascript <br> const numbers = [1, 2, 3]; <br> const doubled = numbers.map(num => num * 2); <br> console.log(doubled); // [2, 4, 6] <br> ``` |
| 52  | What is the `filter()` method in JavaScript?                   | `filter()` creates a new array with all elements that pass the test implemented by the provided function. <br> **Example:** <br> ```javascript <br> const numbers = [1, 2, 3, 4, 5]; <br> const evenNumbers = numbers.filter(num => num % 2 === 0); <br> console.log(evenNumbers); // [2, 4] <br> ``` |
| 53  | What is the `reduce()` method in JavaScript?                   | `reduce()` applies a function against an accumulator and each element to reduce it to a single value. <br> **Example:** <br> ```javascript <br> const numbers = [1, 2, 3]; <br> const sum = numbers.reduce((acc, num) => acc + num, 0); <br> console.log(sum); // 6 <br> ``` |
| 54  | What is the `sort()` method in JavaScript?                     | `sort()` sorts the elements of an array in place and returns the sorted array. <br> **Example:** <br> ```javascript <br> const numbers = [4, 1, 3, 2]; <br> numbers.sort(); <br> console.log(numbers); // [1, 2, 3, 4] <br> ``` |

---

### **Advanced JavaScript (151-500)**

| No. | Question                                                       | Example/Explanation                                            |
|-----|---------------------------------------------------------------|----------------------------------------------------------------|
| 151 | What is a closure and how does it work in JavaScript?          | A closure occurs when a function has access to its lexical scope, even when the function is executed outside that scope. |
| 152 | What is the `setTimeout()` method and how does it work?       | `setTimeout()` is used to delay the execution of a function by a specified amount of time. |
| 153 | How do you handle asynchronous code in JavaScript?            | JavaScript provides mechanisms like callbacks, promises, and async/await to manage asynchronous code. |
| 154 | What is the `async` keyword in JavaScript?                    | `async` is used to define a function that returns a promise, and the function can use `await` for asynchronous operations. |
| 155 | What is the `await` keyword in JavaScript?                    | `await` is used inside an `async` function to pause the execution of the function until the promise resolves. |
| 156 | What is the event loop in JavaScript?                         | The event loop is responsible for executing the code, collecting and processing events, and executing sub-tasks from the event queue. |
| 157 | What are Web Workers in JavaScript?                           | Web Workers allow JavaScript to run scripts in background threads, making it possible to execute code asynchronously without blocking the main thread. |

---


### **Advanced JavaScript (158-250)**

| No.  | Question                                                       | Example/Explanation                                            |
|------|---------------------------------------------------------------|----------------------------------------------------------------|
| 158  | What is the difference between `setTimeout()` and `setInterval()`? | `setTimeout()` executes a function once after a specified delay, while `setInterval()` repeatedly calls a function at specified intervals. <br> **Example:** <br> ```javascript <br> setTimeout(() => console.log("One-time message"), 2000); <br> setInterval(() => console.log("Repeated message"), 2000); <br> ``` |
| 159  | What is a promise chain in JavaScript?                        | A promise chain is a sequence of `.then()` calls where each handler waits for the previous one to resolve. <br> **Example:** <br> ```javascript <br> fetchData().then(result => processData(result)).then(data => displayData(data)); <br> ``` |
| 160  | How can you handle errors in promises?                        | You can handle errors in promises using `.catch()` or `try-catch` with `async/await`. <br> **Example:** <br> ```javascript <br> fetchData().then(result => processData(result)).catch(error => console.log(error)); <br> ``` |
| 161  | What is the `finally()` method in JavaScript promises?        | `finally()` is called after the promise is settled (either resolved or rejected), regardless of its outcome. <br> **Example:** <br> ```javascript <br> fetchData() <br>   .then(result => processData(result)) <br>   .catch(error => console.log(error)) <br>   .finally(() => console.log('Always executed')); <br> ``` |
| 162  | What is `localStorage` in JavaScript?                         | `localStorage` allows you to store data in the browser with no expiration date. The data is stored as key-value pairs. <br> **Example:** <br> ```javascript <br> localStorage.setItem('user', 'Alice'); <br> const user = localStorage.getItem('user'); <br> console.log(user); // 'Alice' <br> ``` |
| 163  | What is the difference between `sessionStorage` and `localStorage`? | `sessionStorage` stores data for the duration of the page session, while `localStorage` persists even after the browser is closed. <br> **Example:** <br> ```javascript <br> sessionStorage.setItem('session', 'active'); <br> localStorage.setItem('user', 'Alice'); <br> ``` |
| 164  | How do you store objects in `localStorage`?                   | `localStorage` stores data as strings, so objects must be serialized using `JSON.stringify()` and deserialized using `JSON.parse()`. <br> **Example:** <br> ```javascript <br> const user = { name: 'Alice', age: 25 }; <br> localStorage.setItem('user', JSON.stringify(user)); <br> const storedUser = JSON.parse(localStorage.getItem('user')); <br> console.log(storedUser); <br> ``` |
| 165  | What are `WebSockets` in JavaScript?                          | `WebSockets` provide a full-duplex communication channel over a single, long-lived connection, enabling real-time communication between the client and server. <br> **Example:** <br> ```javascript <br> const socket = new WebSocket('ws://example.com'); <br> socket.onopen = () => socket.send('Hello Server'); <br> socket.onmessage = (event) => console.log(event.data); <br> ``` |
| 166  | What is the `Proxy` object in JavaScript?                     | A `Proxy` object allows you to create a handler for basic operations (like property lookup, assignment, etc.) on an object. <br> **Example:** <br> ```javascript <br> const handler = { <br>     get: function(target, prop) { <br>         return prop in target ? target[prop] : 37; <br>     } <br> }; <br> const proxy = new Proxy({}, handler); <br> console.log(proxy.someProperty); // 37 <br> ``` |
| 167  | What is the purpose of `Object.freeze()`?                     | `Object.freeze()` prevents modification of existing property attributes and values. <br> **Example:** <br> ```javascript <br> const obj = { name: 'Alice' }; <br> Object.freeze(obj); <br> obj.name = 'Bob'; <br> console.log(obj.name); // 'Alice' <br> ``` |
| 168  | What are `map()` and `filter()` methods in JavaScript?        | `map()` creates a new array by applying a function to each element of the array, while `filter()` creates a new array containing only the elements that pass a specified test. |
| 169  | What is a `Set` in JavaScript?                                | A `Set` is a collection of values where each value must be unique. <br> **Example:** <br> ```javascript <br> const mySet = new Set([1, 2, 3, 3, 4]); <br> console.log(mySet); // Set { 1, 2, 3, 4 } <br> ``` |
| 170  | How do you merge two arrays in JavaScript?                    | You can merge arrays using the `concat()` method or the spread operator. <br> **Example:** <br> ```javascript <br> const arr1 = [1, 2, 3]; <br> const arr2 = [4, 5, 6]; <br> const merged = arr1.concat(arr2); <br> const mergedSpread = [...arr1, ...arr2]; <br> console.log(merged); // [1, 2, 3, 4, 5, 6] <br> ``` |
| 171  | What is `Object.create()` used for in JavaScript?             | `Object.create()` creates a new object with the specified prototype object and properties. <br> **Example:** <br> ```javascript <br> const person = { greet() { console.log('Hello!'); } }; <br> const student = Object.create(person); <br> student.greet(); // 'Hello!' <br> ``` |
| 172  | What is `this` in the context of a method inside an object?   | In the context of an object method, `this` refers to the object itself. |
| 173  | What is the `bind()` method and how is it used?               | The `bind()` method creates a new function that, when invoked, has its `this` value set to the provided object. <br> **Example:** <br> ```javascript <br> function greet() { <br>     console.log(`Hello, ${this.name}`); <br> } <br> const person = { name: 'Alice' }; <br> const boundGreet = greet.bind(person); <br> boundGreet(); // 'Hello, Alice' <br> ``` |
| 174  | What is the difference between `call()` and `apply()`?        | Both methods invoke the function with a specified `this` context. `call()` takes arguments individually, while `apply()` takes arguments as an array. |
| 175  | What is `setImmediate()` and how does it work?                | `setImmediate()` executes a function after the current event loop cycle. |
| 176  | How does `requestAnimationFrame()` work?                      | `requestAnimationFrame()` allows you to schedule a callback to be executed before the next repaint, making it ideal for animations. |
| 177  | What is the `eval()` function in JavaScript?                  | `eval()` evaluates JavaScript code represented as a string and executes it. |
| 178  | What are `WeakMap` and `WeakSet` in JavaScript?                | `WeakMap` and `WeakSet` are collections where the keys (or elements) are weakly referenced, meaning they don't prevent garbage collection of the object. |
| 179  | What is the difference between `undefined` and `not defined`?  | `undefined` means a variable has been declared but hasn't been assigned a value, while `not defined` means the variable hasn't been declared at all. |
| 180  | What is a `Rest` parameter in JavaScript?                      | The `Rest` parameter allows you to represent an indefinite number of arguments as an array. <br> **Example:** <br> ```javascript <br> function sum(...numbers) { <br>     return numbers.reduce((a, b) => a + b, 0); <br> } <br> console.log(sum(1, 2, 3, 4)); // 10 <br> ``` |

---

### **Advanced JavaScript (251-500)**

| No.  | Question                                                       | Example/Explanation                                            |
|------|---------------------------------------------------------------|----------------------------------------------------------------|
| 251  | What are `async` and `await` used for in JavaScript?           | `async` and `await` are used for handling asynchronous operations in a more readable, synchronous

-like manner. |
| 252  | What are Web APIs in JavaScript?                               | Web APIs are built-in browser features that provide functionality for things like DOM manipulation, HTTP requests, local storage, etc. |
| 253  | What is `localStorage` vs `sessionStorage` in JavaScript?       | `localStorage` persists until the browser is closed, while `sessionStorage` lasts only for the duration of a page session. |
| 254  | What is the difference between `null` and `undefined`?         | `null` is explicitly assigned to a variable to indicate "no value," while `undefined` means a variable has been declared but has not been assigned a value. |
| 255  | What is the difference between `for...in` and `for...of` loops? | `for...in` iterates over object properties, while `for...of` iterates over iterable objects (e.g., arrays). |
| 256  | How does event delegation work in JavaScript?                  | Event delegation involves adding a single event listener to a parent element to handle events for child elements. |
| 257  | What is `document.querySelector()` in JavaScript?             | `document.querySelector()` returns the first element that matches a specified CSS selector. |
| 258  | What is a `proxy` in JavaScript?                               | A `proxy` allows you to define custom behavior for fundamental operations (e.g., property access, function calls) on an object. |
| 259  | How does the JavaScript event loop work?                       | The event loop continuously checks the call stack and the message queue and executes events or tasks that are in the queue. |
| 260  | What is the difference between `slice()` and `splice()`?       | `slice()` extracts a section of an array and returns a new array, while `splice()` changes the original array by adding/removing elements. |

---



