# Month 1 Week 2

<style>
  h1 {
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
  }
</style>

---

## Callbacks
A callback is a function that is to be called again even though it is a function itself, but there must another function to be called back. The ‘again’ is the secret to callbacks
The parameters inside a function are not keywords but variables that represent what will be passed nto the function. 
In JavaScript, reduced method can accept 4 parameters. Callbacks have a signature which is a syntax that tells us an example of how we can use them.

```js
function greet(name, callback) {
    console.log(`Hello, ${name}!`);
    callback();
}
function sayGoodbye() {
    console.log("Goodbye!");
}
greet("Ooreoluwa", sayGoodbye);

// Result
// Hello, Ooreoluwa!
// Goodbye!
```

---

There are 3 ways to create events in JavaScript; 
  - HTML attribute, DOM property and addEventListener.

The DOM is JavaScript's object-based representation of your HTML, allowing scripts to control and interact with page elements. HTML IDs become accessible as variables in JavaScript. 

You can access DOM properties using dot (`.`) or bracket (`[]`) notation.

The `addEventListener` method lets you attach multiple event handlers with flexibility and can be removed using `removeEventListener`. 


```js 
const button = document.getElementById("myButton");
button.addEventListener("click", function() {
    console.log("Button clicked!");
});
```

```html
<button id="myButton">Click Me!</button>
```

---

### Promise
A promise is an object representing the future result of an asynchronous operation. Unlike callbacks, promises handle future values with defined states: pending, fulfilled, or rejected. Promises are created using `new Promise()` with `resolve` and `reject` functions. In JavaScript, only falsy values like `null`, `0`, `false`, and `NaN` evaluate to false. `fetch` is a built-in method for making external network requests.


```js
const threePromiseStates = new Promise((resolve, reject) => {
  console.log("Promise is PENDING");
  setTimeout(() => {
    const random = Math.random(3);
    if (random > 0.5) {
      resolve('Promise FULFILLED! Random: 3');
    } else {
      reject('Promise REJECTED! Random too low: 3');}
  }, 2000);
});
threePromiseStates
  .then(result => console.log(result))
  .catch(error => console.error(error));
```

---

### Async/Await

Using `async` before a function makes it return a promise, simplifying asynchronous code. To handle errors with `async/await`, you need to use `try...catch` blocks. `Promise.all` allows multiple promises to run in parallel. Global `await` and Immediately Invoked Function Expressions (IIFE) are also supported. A closure is a function that remembers the variables from its outer scope, even after that scope has closed.


```js
function fetchData() {
  return new Promise((resolve) => {
    setTimeout(() => resolve("Data fetched!"), 1000);
  });}
async function getData() {
  try {
    const result = await fetchData();
    console.log(result); // Output: Data fetched!
  } catch (error) {
    console.error("Error:", error); }}
getData();
```