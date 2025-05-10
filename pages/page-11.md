# Google Meet Class 1

<style>
  h1 {
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
  }
</style>

---

## Module

A **module** is just a file. Modules can load one another and use special directives like `export` and `import` to share functionality. Modularity is a key aspect of large-scale software development, as it helps break a program into separate, interchangeable components that can be reused in different parts of the program.

- The `export` keyword labels variables and functions that should be accessible outside the current module.
- The `import` keyword allows the use of exported content in other modules.

When using multiple script tags, **order is important** — one script must not be loaded before another if it depends on it. Exports must be named exactly as they were declared to ensure they import correctly.

Modules are the **backbone** of how things are done in modern JavaScript.

### Additional Notes

- `as` helps to **rename** imported bindings.
- `import * as name` imports **everything** from a module and stores it in an object called `name`.

---

### Default Import/Export

To use a **default import**, there must be a corresponding `export default` in the module.

- `export default`: Defines the default export of a module.
- The default import can have **any name**, since it's implicitly understood by the module system.

**Key Difference**:

- `export default`: Exports a single value.
- `import * as obj`: Imports all named exports into an object.

---

### Import Maps & Dynamic Imports

- **Import maps** allow you to map a module specifier to a specific URL or path, including JSON and external URLs.
- **Dynamic imports** (`import()`):
  - Look like functions but return **Promises**.
  - Allow modules to be loaded **asynchronously and conditionally**.
  - Only import the module **when needed**.
  - Must be `await`ed before use.
  - Are great for optimizing performance by reducing initial load time.

> Tip: Place dynamic imports **as close as possible** to where they are used.

---

## Bundlers

- **NVM**: Allows managing multiple Node.js versions.
- `npm init`: Initializes a JavaScript project by creating a `package.json` file.
  - `npm init -y` or `npm init --yes`: Quickly creates `package.json` with default values.

---

### Why We Need Bundlers

The **ES Module** system cannot handle certain npm packages directly in the browser. Browsers have limited support for advanced module resolution and cannot understand many file types.

This is where **bundlers** (e.g., Vite, Webpack, Parcel) come in:

- They **bundle and compile** everything into a format the browser can understand.
- Enable importing of non-JavaScript assets like `.png`, `.svg`, and more.
- Make modern JavaScript development practical and scalable.

---

### Summary

- `npm init -y`: Quickly sets up `package.json`.
- **Bundler (e.g., Vite)**:
  - Bundles `main.js` and processes all dependencies.
  - Handles imports like `.png`, `.svg`.
  - Makes everything browser-compatible.
- **ES Modules**:
  - Use `import/export`.
  - Add `type="module"` in the `<script>` tag for proper usage.
  - Rely on the bundler to resolve paths and dependencies.
