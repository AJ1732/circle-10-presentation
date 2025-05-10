# Month 2 Week 2

<style>
  h1 {
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
  }
</style>

---

## Form, Controls

### Overview

- Form properties and methods and examples
- Form Elements
- Form submission: Event and Method submit

### What is Form?

- Forms are fundamental components of web development, enabling users to input data and interact with web applications.
- A solid understanding of how to work with forms and their elements using JavaScript is essential for building dynamic and interactive web pages.
- Forms can be accessed through the document.forms collection, which is a named collection—allowing access to forms by both their name and index.

---
layout: center
class: heading

---

# Form Examples

```html
<form id="myForm">
  <label for="name">Name:</label>
  <input type="text" id="name" name="username" required /><br /><br />
  <label for="email">Email:</label>
  <input type="email" id="email" name="email" required /><br /><br />
  <label for="gender">Gender:</label>
  <select id="gender" name="gender">
    <option value="">Select...</option>
    <option value="male">Male</option>
    <option value="female">Female</option></select
  ><br /><br />
  <textarea name="message" rows="4" cols="30">Enter your message...</textarea
  ><br /><br />
  <button type="submit">Submit</button>
</form>
```

---

## Common Form Elements

Each form element has properties that define its behavior. These are useful in JavaScript, but many can be set as attributes in HTML as well.

| Property   | Description                                                      |
| ---------- | ---------------------------------------------------------------- |
| `value`    | Gets/sets the current value of the form control.                 |
| `name`     | Used to identify the form data after submission.                 |
| `type`     | Specifies the kind of input (`text`, `password`, `email`, etc.). |
| `checked`  | For radio/checkbox to check if it's selected.                    |
| `disabled` | Makes the input ghl                                              |
| `readonly` | Makes the input uneditable but still focusable.                  |

---

| Property      | Description                                              |
| ------------- | -------------------------------------------------------- |
| `required`    | Forces the user to fill out the field before submitting. |
| `placeholder` | Shows hint text in the input.                            |
| `maxlength`   | Limits the number of characters allowed.                 |

---

## Form Submission: submit Event and submit() Method

Form submission is the process by which user-entered data is sent to a server for processing. In JavaScript, form submission can be controlled using:

1. The submit event triggers when the form is submitted, it is usually used to validate the form before sending it to the server or to abort the submission and process it in JavaScript.
2. The method form.submit() allows to initiate form sending from JavaScript. We can use it to dynamically create and send our own forms to server.

---

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Form Submission Example</title>
  </head>
  <body>
    <form id="myForm" action="https://example.com/submit" method="POST">
      <label for="name">Name:</label>
      <input type="text" id="name" name="name" required />
      <button type="submit">Submit</button>
    </form>
  </body>
</html>
```

---

```js
 <script>
    document.addEventListener("DOMContentLoaded", () => {
      const form = document.getElementById("myForm");

      // submit event Listener
      form.addEventListener("submit", function (event) {
        event.preventDefault(); // Prevent default submission
        const name = document.getElementById("name").value;

        if (name.trim() === "") {
          alert("Name is required!");
        } else {
          alert("Form validated. Submitting...");
          // submit programmatically
          form.submit(); // This will elude the submit event
        }
      });
    });
  </script>
```
