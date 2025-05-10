# Month 1 Week 2
Callbacks
A callback is a function that is to be called again even though it is a function itself, but there must another function to be called back. The ‘again’ is the secret to callbacks
The parameters inside a function are not keywords but variables that represent what will be passed nto the function. 
In JavaScript, reduced method can accept 4 parameters. Callbacks have a signature which is a syntax that tells us an example of how we can use them.

```js
function greet(name, callback) {
    console.log('Hello, ${Ooreoluwa!');
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

There are 3 ways to create events in JavaScript; HTML attribute, DOM property and addEventListener.
DOM is the JavaScript representation of your HTML i.e it will extract all the HTML you have on your page and save them into an object so JavaScript can now control the HTML when we write a ‘script.js’. 
Anytime you have an id element in your HTML, that id automatically becomes a variable that you can use in your JavaScript, id automatically becomes core variables
We can access the members of our object through ‘.’ notation or ‘[]’ notation
The addEventListener method allows adding multiple handlers on the same event, with additional configuration options and ability to remove them with ‘removeEventListener’. It is a DOM property cos we can add ‘.’ to it.
‘getData is a function that has 2 callbacks; it accepts data and it accepts an error.

```js const button = document.getElementById("myButton");
button.addEventListener("click", function() {
    console.log("Button clicked!");
});
```

```html
<button id="myButton">Click Me!</button>
```
---

A promise is an object that represents a future result of an asynchronous operation. Difference between a callback and a promise is that callback happens when it happens but with promise, it is a future that we don’t know
A promise has 3 states; pending, fulfilled or rejected. 
We create a promise by writing ‘newPromise()’. When declaring a promos, give it 2 functions- a resolve or a rejection. Everything in JavaScript is true except falsey values e.g., null, zero, false itself, NaN, etc
Fetch is an inbuilt mechanism to communicate with an external resource.

```js
const threePromiseStates = new Promise((resolve, reject) => {
  console.log("Promise will be FULFILLED");
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

Async and await
By putting async in front of an ordinary function, the function automatically behaves like a promise. It makes the creation of promise very easy to do. 
The only problem with async and await is that it does not give us a good way to catch errors, in order to do this, we need to write the function again and there must be something called a ‘try’ and ‘catch’ if there is a problem. We also have global await and immediately invoked function condition, IIFC
promise.all gives all the ability to run 2 promises together, it runs them in a parallel. You can also promisify an existing callback
A closure is a function that returns a function, it is a function that has memory to remember what is inside of it

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