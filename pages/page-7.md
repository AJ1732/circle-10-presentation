
# Month 2 Week 1 

<style>
  h1 {
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
  }
</style>

---

## Summary of DOM Operations this Semester


<style>
  h2 {
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
  }
</style>


---

## 1. Searching & Changing the DOM

```js
const app = document.querySelector("#app");
app.innerHTML = "<div>Hello world</div>";
app.style.color = "red";

```

---

## 2. Creating & Appending Elements

```js
const div = document.createElement("div");
div.textContent = "Hello world - Setemi";
app.appendChild(div);
```

THE FINAL HTML

```html
<div id="app">
  <div style="color: red;">Hello World</div>
  <div>Hello world - Setemi</div>
</div>
```

---

## 3.  Removing & Replacing Nodes

```js
const newNode = document.createElement("div");
newNode.textContent = "New Text";
app.replaceChild(newNode, elem.firstChild);

```


FINAL HTML
```html
<div id="app">
  <div>New Text</div>
  <div>Hello world - Setemi</div>
</div>

```

Then to remove the app element
```js
app.remove(); // removes the element entirely
```


---

## 4.  Handling Events & Updating DOM

```js

const app = document.getElementById("counter");
const update = document.getElementById("update"); // tHis is a button


let counter = 0;
update.addEventListener("click", () => {
  app.children[0].textContent = `Updated ${counter++}`;
});

```

---

## 5. Event Bubbling & Capturing

When an event is triggered, it moves in two phases—capturing (from top to target) and bubbling (from target to top). You can listen to events in either phase using the capture option.

```js
// This listener will fire during the bubbling phase (default)
elem.addEventListener("click", listener);

// This one will fire during the capturing phase (top-down)
parent.addEventListener("click", listener, { capture: true });

```

---

## 6.  Event Delegation

Rather than attaching event listeners to each individual child element, event delegation attaches one listener to a common ancestor and checks the target.

```js
menu.onclick = function (event) {
  // Only respond if the clicked element is a <li>
  if (event.target.tagName === "LI") {
    console.log(event.target.innerHTML);
  }
};


```

---

## 7. Prevent Default & Custom Events

Explanation:

preventDefault() stops the browser’s default behavior (e.g., form submission or right-click menu).

stopPropagation() prevents the event from bubbling further.

You can also dispatch custom events using the Event constructor.

```js
// Prevent right-click menu and stop bubbling
elem.oncontextmenu = function (e) {
  e.preventDefault(); 
  e.stopPropagation();
};

// Create and dispatch a custom event named 'hello'
const hello = new Event("hello", { bubbles: true });
elem.dispatchEvent(hello);

```

---

## 8.  Event Object
When an event occurs, the browser creates an event object with useful data like the mouse position or event phase. You can access this object inside your event handler.

```js
elem.addEventListener("click", (event) => {
  console.log("X:", event.clientX, "Y:", event.clientY); // Mouse coordinates
  console.log("Target:", event.currentTarget); // The element that handled the event
  console.log("Phase:", event.eventPhase); // 1 (Capturing), 2 (Target), 3 (Bubbling)
});

```
