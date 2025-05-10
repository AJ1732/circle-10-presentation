# Google Meet Class 1

<style>
  h1 {
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
  }
</style>

---

## What is a Module?

A **module** is just a file that exports functions, objects, or values to be reused elsewhere.

```js
// greet.js
export const greet = () => console.log("Hello!");
```

```js
// main.js
import { greet } from "./greet.js";
greet(); // Hello!
```

* `export` makes a value available to other files.
* `import` brings in functionality from other modules.

> ✅ Helps break large codebases into manageable pieces.

---

#### 🔁 Default vs Named Exports

```js
// utils.js
export default function sayHi() {
  console.log("Hi!");
}
```

```js
// main.js
import sayHi from "./utils.js";
sayHi(); // Hi!
```

* `export default` allows one default export per file.
* Default imports can have any name:

```js
import anything from "./utils.js";
```

> Use when exporting a **single main function or object**.

---

#### 📦 Import Maps & Dynamic Imports

```js
// Dynamically import when needed
button.addEventListener("click", async () => {
  const module = await import("./math.js");
  console.log(module.add(2, 3));
});
```

* Loads modules **only when needed**.
* Improves performance by **reducing initial load size**.

> ⚠️ Must use `await` or `.then()` to handle the Promise.

---

#### 🛠 Why Use Bundlers (Vite, Webpack)?

```bash
npm init -y        # Initialize project
npm install vite   # Install bundler
```

```js
// vite.config.js (example)
export default {
  root: "./src",
};
```

* Converts ES modules and other assets (`.svg`, `.png`, `.css`) into a format browsers can understand.
* Solves browser limitations with module resolution.

> 🧠 Think of bundlers as translators between your modern code and the browser.
