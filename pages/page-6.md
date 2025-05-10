# Month 1 Week 4

<style>
  h1 {
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
  }
</style>

---


### Window, DOM, CSSOM, BOM

- **Window**: the global object representing the browser window; entry point to all web APIs.
- **DOM (Document Object Model)**: object‐based representation of the HTML document structure.
- **CSSOM (CSS Object Model)**: the object model of all CSS styles applied, enabling dynamic style manipulation.
- **BOM (Browser Object Model)**: provides access to browser components i.e window (e.g., `navigator`, `location`, `history`).

<br />

> The host environment (browser) provides the DOM/BOM objects, and ECMAScript is the language used to manipulate them dynamically.

<br />

> **Why place `<script>` in `<head>` vs. bottom of `<body>`?**
<!-- > - In `<head>`: scripts load before content, blocking rendering—useful for critical polyfills.
> - At end of `<body>`: page renders first, then scripts execute; improves perceived load speed. -->


---

<p>
  Traversing the DOM Tree is conceptually similar to walking a data‑structure
  <code>Tree</code>. You start at one node and move to its parent, children, or siblings.
</p>

<ul>
  <li><strong>Root to leaf:</strong> Start at <code>document.documentElement</code> and drill down via <code>children</code>.</li>
  <li><strong>Siblings:</strong> Move sideways using <code>nextSibling</code> / <code>previousSibling</code>.</li>
  <li><strong>Parent:</strong> Go up via <code>parentNode</code> or <code>parentElement</code>.</li>
  <li><strong>Finding by ID:</strong> Kick‑off traversal at a specific node with <code>getElementById</code>.</li>
</ul>

---

```js
// Get a starting element
const element = document.getElementById("text");

// Traverse to parent
const parent = element.parentElement;
console.log("Parent node:", parent);

// Traverse to children
const firstChild = element.children[0];
console.log("First child:", firstChild);

// Traverse to siblings
const next = element.nextElementSibling;
const prev = element.previousElementSibling;
console.log("Next sibling:", next, "Previous sibling:", prev);

// Walk entire subtree
function walk(node) {
  console.log("Visiting:", node);
  for (const child of node.children) {
    walk(child);
  }
}
// start full-tree traversal
walk(document.body);
```

---

- <strong>Live Selectors (auto‑update):</strong> These are DOM methods that return a <em>live</em> <code>HTMLCollection</code>

  they automatically reflect changes in the DOM as elements are added or removed. Examples include:

  <ul>
    <li><code>getElementsByTagName(tagName)</code></li>
    <li><code>getElementsByClassName(className)</code></li>
    <li><code>getElementsByName(name)</code></li>
  </ul>

  <!-- <p><em>This “live” behavior means if you dynamically add or remove elements that match the selector, the collection updates in real time—no need to re-query the DOM. This can be powerful but also tricky if you're not aware it's happening.</em></p> -->
