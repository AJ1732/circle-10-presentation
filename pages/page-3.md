# Month 1 Week 1

<style>
  h1 {
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
  }
</style>

---

## What is the 'return' Statement?

<p>It is last command of every function and used to output a value</p>

- Return a `number`

```js
function double(number) {
  return number * 2;
}
console.log(double(5)); // Output: 10
```

- Return an `Object`

```js
function name(firstName, lastName) {
  return { firstName, lastName };
}
console.log(name("Setemi", "Ojo")); // Output: { firstName: "Setemi", lastName: "Ojo" }
```

- Return an `Array`

```js
function numbers(a, b, c) {
  return [a, b, c];
}
console.log(numbers(1, 2, 3)); // Output: [1, 2, 3]
```

---

## What are Arrays?

Arrays are data structures used for storing data like `Objects`, `numbers`, `strings`. <br />
They can be declared using;

- literal notation `[]`

```js
const arr1 = [1, 2, 3];
console.log(arr1); // Output: [1, 2, 3];
```

- Array constructor `new Array()`

```js
const arr2 = new Array("a", "b", "c");
console.log(arr1); // Output: ['a', 'b', 'c'];
```

---

## What are Rest Parameters & Spread Operators

<div class="grid grid-cols-2 gap-x-4 mt-4">
<!-- LEFT COLUMN -->
<div v-click>

### Rest Parameters

- Gathers multiple values into a single array
- Used in **function parameters** with `...`(spread operator)
- It's useful when you don’t know how many arguments a function will receive.

  ```js
  function printAfter2(first, second, ...rest) {
    console.log(rest);
  }
  printAfter2("Musa");
  // Output: ["Musa"]
  ```

  </div>

<!-- RIGHT COLUMN -->
<div v-click="2">

### What is the Spread Operator?

- Used to unpack or spread _(yes, like butter)_ out iterable data structures.

```js
const first = [1, 2];
const second = [3, 4];

const combined = [...first, ...second];

console.log(combined); // Output: [1, 2, 3, 4]
```

- It looks the same as the rest parameter (...), but its purpose is the opposite:
  - Rest Parameter collects, when at the end of the function.
  - Spread Operator expands _occurs in a function call_.
  </div>
  </div>

<p v-click="3" class="-mt-4">

- Similaries include; Used to clone iterate data structures .eg strings, objects, arrays - uses `...`
</p>

---

## Callback Functions

Simply put, a function called by another function

```js
function callbackEx(message, yesFn, noFn) {
  let result = confirm(message);
  if (result) yesFn();
  noFn();
}
callBackEx(
  "Do you have a boyfriend",
  () => console.log("yes"),
  () => console.log("no")
);
```

<!-- STYLES -->
<style>
  li {
    font-size: 0.875rem;
  }
</style>
