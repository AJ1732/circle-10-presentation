# Month 1 Week 1

<br />

## Return Statement in JavaScript

<br />

## What is `Return Statement`?

- Tell the function to stop executing and return a value to the caller.
- Sends a value back to the caller when the function is being called.
- If `return` is not used, the function will automatically return `undefined` by default.

## Key Points

- `return` can return **any data type**
- Code after `return` **won’t run**
- Only **one value** can be returned (use objects/arrays to group values)
- When `return`is absent , the function returns **undefined**
- We cant have multiple `return` statements in a function (except in some cases)e.g `return` in `if`/`else` statements.

---

## 🔹 Example 1: Returning a Value

```js
function double(number) {
  return number * 2;
}

console.log(double(5)); // Output: 10
```
## Rest Parameter & Spread Operator
---

# What is the Rest Parameter?

- Gathers multiple values into a single array
- Used in **function parameters** with `...`(spread operator)
- It's useful when you don’t know how many arguments a function will receive.

---

### Rest Parameter Example

```js
function printNames(...names) {
  console.log(names);
}

printNames("Ali", "Zara", "Musa");
// Output: ["Ali", "Zara", "Musa"]
```
## Spread Operator
---
# What is the Spread Operator?
- The spread operator (...) is used to unpack or spread out elements from an array, object, or string.It looks the same as the rest parameter (...), but its purpose is the opposite:.
- Rest Parameter collects.
- Spread Operator expands.

### Spread Operator Example

```js
const first = [1, 2];
const second = [3, 4];

const combined = [...first, ...second];

console.log(combined); // Output: [1, 2, 3, 4]

```