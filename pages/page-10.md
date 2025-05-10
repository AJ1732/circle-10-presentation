# Month 2 Week 4

<style>
  h1 {
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
  }
</style>

---

## Pure JavsScript to React

A tiny helper that mimics React’s `createElement` in vanilla JS:
it creates an element, applies props (including one‑time event listeners), and inserts children

```js
const makeElement = (elementType, props, children) => {
  const element = document.createElement(elemeType);

  if (props) {
    for (const [key, value] of Object.entries(props)) {
      if (key === "onclick" && props["once"]) {
        element.addEvemtListener("click", value, { once: true });
      } else {
        element[key] = value;
      }
    }
  }

  if (children) {
    element.prepend(...children);
  }

  return element;
};
```

---

| Name           | Type                | Description                                                                                     |
| -------------- | ------------------- | ----------------------------------------------------------------------------------------------- |
| `elementType`  | `string`            | Tag name of the element to create (e.g. `"div"`, `"h1"`, `"button"`).                           |
| `props`        | `object` (optional) | Attributes, properties, and event handlers. To use a one‑time click handler include `once: true`, `onclick`, `class` |
| `children`     | `Array<Node>`       | An array of child **nodes**—either text nodes (e.g. `"hello"`) or elements via `makeElement`.      |


---

- Valid tags: elementType must be a valid HTML tag name (e.g. "p", "span", "ul").

- Props object example:

```js
{
  className: "bg-red-500",
  onclick: () => alert("clicked"),
  once: true
}
```

- Children must be passed in an array. You can mix text and elements:

```js
const btn = makeElement(
  "button",
  { onclick: () => alert("remove"), once: true },
  ["✕"]    
);
```

```js
const item = makeElement(
  'li', 
  {style: 'display: flex;'},
  [btn]
)
```

