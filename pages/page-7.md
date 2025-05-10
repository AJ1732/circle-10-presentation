
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


JavaScript. Here's what your presentation includes: ✅ Key DOM Topics Covered:


---

## 1. Searching the DOM

```js
// Example: find the element with id "app"
let elem = document.querySelector("#app");
elem.innerHTML = "<div>Hello world</div>";
elem.style.color = "red";

// Or you can use the ID directly if assigned to a variable
app.style.color = "red";
app.innerHTML = "<div>Hello</div>";
```

---

## 2. Changing the DOM

```js
const elem = document.querySelector("#app");
elem.innerHTML = `<div>Hello world, update your name</div>`;
```

---

## 3. Adding Text Content

```js
const elem = document.querySelector("#app");
const newElem = document.createElement("div");
const textContent = document.createTextNode("Hello world - Setemi");
newElem.appendChild(textContent);
elem.appendChild(newElem);

// Add comments:
const comment = document.createComment("This is a comment");
elem.appendChild(comment);
```

---

## 4. Removing Nodes

```js
// Using remove() method to remove. Be careful—remove() deletes the element and its children:
const elem = document.querySelector("#app");
elem.remove();

// Wrap children in a span to preserve parts if needed.
```

---

## 5. Updating Text

```js
// Using operator +=
const elem = document.querySelector('#app')
elem.textContent + = 'Updated'

// Using replace
const newElem = document.createElement("div");
newElem.textContent = "New Text";
elem.replaceChild(newElem, elem.firstChild);


```

---

## 6. Simple Counter with Events

```js
// Using event and counter to update text/count
let counter = 0;
const elem = document.querySelector("#app");
elem.innerHTML = `
  <div>Hello ${counter}</div>
  <button id="update">Update</button>
`;

update.addEventListener("click", () => {
  elem.children[0].textContent = `Hello world updated ${counter++}`;
});
```

---

## 7. Events and Listeners

```js
// There are three ways to event
// HTML approach, addEventListener approach, dom approach
function setupCounter(elem) {
  let counter = 0;
  const setCounter = (count) => {
    counter = count;
    elem.innerHTML = `Counter is ${counter}`;
  };
  elem.addEventListener("click", () => setCounter(counter + 1));
  setCounter(0);
}
```

---

## 8. Bubbling & Capturing

```js
//use bubble phase
const elem = document.querySelector("h1");
const handler = ()=> alert('click');
elem.addEventListener('click', handler, { once: true})


// use capture phase its a defsault
function listener(e) {
  console.log("Click:", e.currentTarget.tagName);
}

elem.addEventListener("click", listener);
parent.addEventListener("click", listener);
grandParent.addEventListener("click", listener);

//enable capture by adding true
document.querySelectorAll("*").forEach((elem) => {
  elem.addEventListener("click", listener, { capture: true });
});



```

---

## 9. Event Delegation

```html
<ul id="menu">
  <li>Home</li>
  <li>About</li>
</ul>
```

```js
// Involves adding single event listen to common parent rather than all
const menu = document.getElementById("menu");
menu.onclick = function (event) {
  const target = event.target;
  if (target.tagName != "LI") {
    console.log(target.innerHTML);
  }
};
```

---

## 10. Prevent Default & Stop Propagation

```js
// To prevent the default behaviour 
document.querySelector("h1").oncontextmenu = function (e) {
  e.stopPropagation();
  e.preventDefault();
};
```

---

## 11. Dispatching Custom Events

```js
// Away to ctreate our custom event 
const hello = new Event("hello", {
  bubbles: true,
  cancelable: true,
});

elem.addEventListener("hello", function (event) {
  alert("Hello from: " + event.target.tagName);
});

elem.dispatchEvent(hello);
```

---

## 12. Event Object Details

```js
//When event happen browser create details and put in it pass it as agument to handler
const elem = document.querySelector("h1");

elem.addEventListener("click", function (event) {
  console.log(event.currentTarget); // Current element
  console.log(event.eventPhase); // Capturing/Bubbling
  console.log(event.clientX, event.clientY); // Mouse coordinates
});
```

