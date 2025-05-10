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

- <strong>Live Selectors (auto‑update):</strong> These are DOM methods that return a <em>live</em> <code>HTMLCollection</code>

  they automatically reflect changes in the DOM as elements are added or removed. Examples include:

  <ul>
    <li><code>getElementsById(idName)</code></li>
    <li><code>getElementsByTagName(tagName)</code></li>
    <li><code>getElementsByClassName(className)</code></li>
    <li><code>getElementsByName(name)</code></li>
  </ul>

  <!-- <p><em>This “live” behavior means if you dynamically add or remove elements that match the selector, the collection updates in real time—no need to re-query the DOM. This can be powerful but also tricky if you're not aware it's happening.</em></p> -->
