## Month-2-Week-2

## This concept of Todo introduces you to the bundles that we are going to have

---

1. ## Getting the DOM and Creating the Todo App

```js
const todosDisplay = document.querySelector('section.display-todos ol');
const todoInput = todoForm.querySelector('#todo');

function todoFormSubmitHandler(event) {
  event.preventDefault();

  const formData = new FormData(todoForm);
  const todoValue = formData.get('todo');

  if (!todoValue.trim()) return;

  const todoText = document.createTextNode(todoValue.trim());
  const todoLi = document.createElement('li');
  const todoDeleteSpan = document.createElement('span');

  todoDeleteSpan.classList.add('delete');
  todoDeleteSpan.textContent = 'X';
  todoDeleteSpan.setAttribute('title', `Delete ${todoValue.trim()}`);
  todoDeleteSpan.onclick = function () {
    todoLi.remove();
  };

  todoLi.append(todoText, todoDeleteSpan);
  todosDisplay.appendChild(todoLi);

  todoInput.value = '';
  todoForm.reset();
}

todoForm.addEventListener('submit', todoFormSubmitHandler);
```

---

2. ## Example of the Form We Use

```html
<form action="" id="todoForm" novalidate>
  <div class="form-input">
    <label for="todo"></label>
    <input
      type="text"
      id="todo"
      name="todo"
      placeholder="Enter todo"
      required
      minlength="2"
      maxlength="100"
    />
  </div>
  <button>Create Todo</button>
</form>
```

---

3. ## Section of the Todo List

```html
<section class="display-todos">
  <ol id="todosDisplay">
    <li>
      Dance <span>X</span>
    </li>
    <li>
      Eat <span>X</span>
    </li>
    <li>
      Code <span>X</span>
    </li>
  </ol>
</section>
```

---

4. ## Handling Form Submission

```html
<!-- Form submission allows users to input data and send it to the server for processing -->
<!-- In JavaScript, we have two primary ways to handle form submission:
1. Submit event
2. form.submit() -->

<form method="post" action="" id="todoForm" novalidate>
  <input type="text" name="" />
</form>

<script>
  const form = document.querySelector('form');
  form.addEventListener('submit', function (event) {
    event.preventDefault();
    console.log('Form submitted');
  });
</script>

<!-- Three common HTTP methods:
- POST
- GET
- DIALOG (not widely used) -->
```

---

5. ## Basic Submit Event Handling and Validation

```js
const form = document.querySelector('form');
const nameInput = document.querySelector('#name');
const emailInput = document.querySelector('#email');

form.addEventListener('submit', function (event) {
  let isValid = true;

  if (nameInput.value.trim() === '') {
    isValid = false;
    console.error('Name is required');
  }

  if (!isValidEmail(emailInput.value)) {
    isValid = false;
    console.error('Invalid email address');
  }

  if (!isValid) {
    event.preventDefault();
  }
});

function isValidEmail(email) {
  const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
  return emailRegex.test(email);
}
```

---

6. ## Relationship Between `submit` and `click` Events

```html
<form id="myForm">
  <input type="text" id="name" placeholder="Enter your name" />
  <input type="email" id="email" placeholder="Enter your email" />
  <input type="submit" value="Submit" />
</form>

<script>
  const form = document.getElementById('myForm');
  const submitButton = form.querySelector('input[type="submit"]');

  form.addEventListener('submit', function (event) {
    console.log('Form submitted');
  });

  submitButton.addEventListener('click', function (event) {
    console.log('Submit button clicked');
  });
</script>
```

---

7. ## `form.submit()` Method

```js
function createAndSubmit() {
  const form = document.createElement('form');
  form.method = 'post';
  form.action = './api/submit';

  const nameInput = document.createElement('input');
  nameInput.type = 'text';
  nameInput.name = 'username';
  nameInput.value = 'John';

  form.appendChild(nameInput);
  document.body.appendChild(form);

  form.submit(); // Note: This will not trigger the submit event
}

createAndSubmit();
```

---

8. ## Form Validation

```html
<!-- Form validation ensures data submitted by users is correct, complete, and secure.
Key aspects of validation include:
1. novalidate attribute
2. HTML validation attributes
3. Constraint Validation API -->

<form novalidate>
  <label for="email"></label>
  <input type="email" id="email" required />
</form>

<!-- HTML validation attributes:
- required
- minlength
- maxlength
- pattern (regex)
- type -->
```

---

9. ## Constraint Validity Example

```html
<form id="myForm">
  <label for="email">Email:</label>
  <input type="email" id="email" required />
  <span id="emailError"></span>
  <button type="submit">Submit</button>
</form>

<script>
  const form = document.getElementById('myForm');
  const email = document.getElementById('email');
  const emailError = document.getElementById('emailError');

  email.addEventListener('input', function () {
    if (email.validity.typeMismatch) {
      email.setCustomValidity('Please enter a valid email address');
      emailError.textContent = email.validationMessage;
    } else {
      email.setCustomValidity('');
      emailError.textContent = '';
    }
  });

  form.addEventListener('submit', function (event) {
    if (!email.checkValidity()) {
      event.preventDefault();
      emailError.textContent = email.validationMessage;
    }
  });
</script>
```

---

### Thank you.
