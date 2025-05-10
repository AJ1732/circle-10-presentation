# Month 1 Week 3

<style>
  h1 {
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
  }
</style>

---  

## What is a REST API?

**REST** = Representational State Transfer  
A way to build APIs for communication over HTTP.
### key note

- There is no session or memory of past interactions between client and server.
- Uses HTTP methods (GET, POST, PUT, DELETE).
- Returns data in JSON or XML.

**Example:**  
`https://jsonplaceholder.typicode.com/todos/1`

---

## What is a Network Request?

A **network request** is how apps talk to servers.  
Usually made through HTTP methods:

- **GET** – retrieve data  
- **POST** – send data  
- **PUT** – update data  
- **DELETE** – remove data  

You use them when your app needs to read/write data online.


---

## 🔍 GET Request

```js
fetch('https://api.example.com/users')
  .then(res => res.json())
  .then(data => console.log(data));
```
<br />

## Example: POST Request

```js
fetch('https://api.example.com/users', {
  method: 'POST',
  headers: {
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({
    name: 'CodeRheem',
    email: 'coderheem@example.com'
  })
})
.then(response => response.json())
.then(data => console.log(data))
.catch(error => console.error('Error:', error));
```

- This sends user data to the server and logs the response.

---

## PUT Request

```js
fetch('https://api.example.com/users/1', {
  method: 'PUT',
  headers: { 'Content-Type': 'application/json' },
  body: JSON.stringify({ name: 'Updated CodeRheem' })
})
.then(res => res.json())
.then(data => console.log(data));
```

<br />

## DELETE Request

```js
fetch('https://api.example.com/users/1', {
  method: 'DELETE'
})
.then(() => console.log('User deleted'));
```

