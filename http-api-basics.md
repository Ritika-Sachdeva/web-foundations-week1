#  HTTP & REST APIs

## 1️. What is an API?
- An API (Application Programming Interface) is like a messenger between two software systems.
- It allows the frontend (browser) and backend (server/database) to communicate.
- APIs send requests and receive responses.

### Real-Life Analogy
- Imagine you're at a restaurant:
  - You (frontend) order pizza.
  - Waiter (API) takes your order.
  - Kitchen (backend) prepares it.
  - Waiter brings the pizza to you.

---

## 2️. What Happens in an API Request?
- **Method** – The type of request (GET, POST, PUT, DELETE).
- **URL** – The address of the API endpoint.
- **Headers** – Extra information like content type or authentication.
- **Body** – The data you send (only for POST/PUT requests).

---

## 3️. What is JSON?
- JSON stands for JavaScript Object Notation.
- It is a lightweight format for storing and transferring data.
- Easy to read and write.
- Works with almost all programming languages.(**language-independent**)
- Used by most APIs for communication.

Example:
```json
{
  "name": "Ritika",
  "age": 22
}
```

#  Difference Between JSON and Regular JavaScript Objects

- JSON is always written as a **string** with a fixed structure, while a JavaScript object is stored directly in memory as an object.  
- JSON keys and string values must always use **double quotes**, but JavaScript objects can use single quotes or no quotes for keys.  
- JSON cannot contain **functions, undefined, or special JS types**, but JavaScript objects can.  
- JSON does not allow **comments**, while JavaScript objects can include comments in code.  
- JSON supports only basic data types like string, number, boolean, array, object, and `null`, whereas JavaScript objects support all JavaScript data types.  
- JSON is mainly used for **data transfer between systems**, while JavaScript objects are used for working with data directly in JavaScript programs.  

## Why JSON is Used Widely in APIs

- **Lightweight and Fast:** JSON has a simple, minimal syntax, so it’s faster to parse and transmit compared to XML.  
- **Human-Readable:** Its key-value format is easy for humans to read and write.  
- **Language-Independent:** JSON can be used by almost every programming language, making it perfect for cross-platform communication.  
- **Easy Integration with JavaScript:** JSON structure matches JavaScript objects, so working with it in web apps is seamless.  
- **Less Overhead than XML:** JSON does not require closing tags like XML, reducing data size.  
- **Better than Plain Text:** Plain text can’t represent complex data structures like arrays and nested objects, while JSON can.


## Step 2 – Explore a Public REST API

For this task, I explored the **JSONPlaceholder** API using Postman and my browser.

---

### 1️. GET Request – Fetch All Users

- **HTTP Method:** GET  
- **Request URL:**  

https://jsonplaceholder.typicode.com/users
 **Status Code:** `200 OK` 
- **Response Body (truncated example):**
```json
[
{
  "id": 1,
  "name": "Leanne Graham",
  "username": "Bret",
  "email": "Sincere@april.biz"
},
{
  "id": 2,
  "name": "Ervin Howell",
  "username": "Antonette",
  "email": "Shanna@melissa.tv"
}
]
```
### 2.POST Request – Create a New Post

- **HTTP Method:** POST  
- **Status Code:** 201 Created
- **Request URL:**  
https://jsonplaceholder.typicode.com/posts
- **Request Body:**
```json
{
"title": "Learning APIs",
"body": "APIs are awesome!",
"userId": 1
}
```
**Response Body**
```json
{
  "title": "Learning APIs",
  "body": "APIs are awesome!",
  "userId": 1,
  "id": 101
}
```

## Step 3 – Reflection on What I Observed

---

### 1️. Difference Between GET, POST, PUT, and DELETE (with real-world examples)

- **GET** – Used to retrieve data from the server without making changes.  
  *Example:* Viewing a list of blog posts on a website.

- **POST** – Used to create a new resource on the server.  
  *Example:* Submitting a registration form to create a new user account.

- **PUT** – Used to fully update/replace an existing resource.  
  *Example:* Updating an employee's complete profile in a company database.

- **DELETE** – Used to remove a resource from the server.  
  *Example:* Deleting a product from an online store’s inventory.

---

### 2️. Major Categories of HTTP Status Codes (and examples I saw)

- **2xx – Success**  
  The request worked as intended.  
  *Example:* `200 OK` (GET request success), `201 Created` (POST request success).

- **4xx – Client Error**  
  The request had an issue on the client side.  
  *Example:* `404 Not Found` (resource doesn’t exist).

- **5xx – Server Error**  
  The server failed to process a valid request.  
  *Example:* `500 Internal Server Error` (unexpected server issue).

 **Why They Matter:**  
Status codes help the client understand exactly what happened — whether the request was successful, failed due to bad input, or failed due to a server issue.

---

### 3️. What Are HTTP Headers? (and one I observed)

- **Definition:** HTTP headers are key-value pairs sent along with requests and responses to give extra information about the data or instructions for processing it.

- **Example Observed:**  
  `Content-Type: application/json`  
  *Importance:* It tells the server or client that the body of the request/response is in JSON format, so it can be parsed correctly.

---

## Key Takeaways

- **How APIs Work:** APIs allow two systems to communicate by sending requests and receiving responses, usually in JSON format, over HTTP methods like GET, POST, PUT, and DELETE.

- **What’s Important in an HTTP Request:** The HTTP method, the request URL, headers (like `Content-Type`), and the request body (if any) are all crucial for telling the server what you want and how you’re sending the data.

- **How Understanding HTTP Helps as a Developer:** Knowing how HTTP works makes it easier to debug API issues, integrate with external services, optimize performance, and ensure secure, correct data transfer between client and server.

**EXAMPLE:** Food Delivery app

