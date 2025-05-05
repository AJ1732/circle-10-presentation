---
theme: excali-slide
background: https://cover.sli.dev

title: Welcome to Slidev
info: |
  ## Slidev Starter Template
  Presentation slides for developers.
  Learn more at [Sli.dev](https://sli.dev)
class: text-center
# https://sli.dev/features/drawing
drawings:
  persist: false
# slide transition: https://sli.dev/guide/animations.html#slide-transitions
transition: slide-left
# enable MDC Syntax: https://sli.dev/features/mdc
mdc: true
# open graph
seoMeta:
  ogImage: https://cover.sli.dev

# Page 1 Source
src: ./pages/page-1.md
---

---
transition: fade-out
layout: two-cols
layoutClass: gap-16

src: ./pages/page-2.md
---
---
# Return Statement in JavaScript
---
## What is `Return Statement`?

- Tell the function to stop executing and return a value to the caller.
- Sends a value back to the caller when the function is being called.
- If `return` is not used, the function will automatically return `undefined` by default.

---

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
---
transition: slide-up

src: ./pages/page-3.md
---

---
transition: slide-up

src: ./pages/page-4.md
---

---
transition: slide-up

src: ./pages/page-5.md
---

---
transition: slide-up

src: ./pages/page-6.md
---

---
transition: slide-up

src: ./pages/page-7.md
---

---
transition: slide-up

src: ./pages/page-8.md
---

---
transition: slide-up

src: ./pages/page-9.md
---

---
transition: slide-up

src: ./pages/page-10.md
---

---
transition: slide-up

src: ./pages/page-11.md
---

---
transition: slide-up

src: ./pages/page-12.md
---

---
transition: slide-up

src: ./pages/page-13.md
---