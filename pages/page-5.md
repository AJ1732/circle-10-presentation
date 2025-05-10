# Month 1 Week 3
---  

## What is a REST API?

**REST** = Representational State Transfer  
A way to build APIs for communication over HTTP.
### key note

- There is no session or memory of past interactions between client and server.
- Uses HTTP methods (GET, POST, PUT, DELETE).
- Returns data in JSON or XML.

**Example:**  
`https://api.example.com/users`

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

## What is a POST Request?

A **POST request** is used to **send data to a server**.

- Often used for creating new records
- Data goes in the **request body**
- Requires headers (like `Content-Type`)

Used heavily in forms, sign-ups, etc.

---

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

## 🔍 GET Request

**GET** is used to **retrieve** data from a server.  
It **does not** modify anything — just fetches info.

###  Use Case:  
- Show a list of users  
- Get details of a product

```js
fetch('https://api.example.com/users')
  .then(res => res.json())
  .then(data => console.log(data));
```

---

## PUT Request

**PUT** is used to **update** an existing resource.  
You must send the full updated object.

### Use Case:  
- Edit a user's profile info

```js
fetch('https://api.example.com/users/1', {
  method: 'PUT',
  headers: { 'Content-Type': 'application/json' },
  body: JSON.stringify({ name: 'Updated CodeRheem' })
})
.then(res => res.json())
.then(data => console.log(data));
```

---

## DELETE Request

**DELETE** is used to **remove** a resource from the server.

### Use Case:  
- Delete a user account  
- Remove a post

```js
fetch('https://api.example.com/users/1', {
  method: 'DELETE'
})
.then(() => console.log('User deleted'));
```

---
