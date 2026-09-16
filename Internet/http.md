# What Is HTTP?

> **HTTP** stands for **HyperText Transfer Protocol**. It is a protocol used for communication between clients and servers on the web. HTTP defines how a client asks a server for something and how the server responds.

```text
Browser
   |
   | HTTP Request
   ↓
Server
   |
   | HTTP Response
   ↓
Browser
```

HTTP is an **application-layer protocol**.

---

## HTTP Request

An HTTP request is sent by a client to a server.

A simplified request looks like:

```text
GET /products HTTP/1.1
Host: example.com
```

An HTTP request can contain several important parts:

```text
HTTP Request
│
├── Method
├── URL / Path
├── Headers
└── Body
```

### HTTP Methods

HTTP methods describe what the client wants to do.

Common methods include:

```text
GET
POST
PUT
PATCH
DELETE
```

### GET

Used to request data.

```http
GET /products
```

Example:

```text
Browser → "Give me the products."
```

### POST

Used to send data to a server.

```http
POST /users
```

For example, submitting a registration form.

```text
Browser → "Create a new user using this information."
```

### PUT

Usually used to replace an existing resource.

```http
PUT /users/10
```

### PATCH

Used to partially update a resource.

```http
PATCH /users/10
```

For example, changing only a user's name.

### DELETE

Used to delete a resource.

```http
DELETE /users/10
```

---

## HTTP Response

After receiving a request, the server sends an HTTP response.

A simplified response looks like:

```text
HTTP/1.1 200 OK

{
    "message": "Success"
}
```

An HTTP response generally contains:

```text
HTTP Response
│
├── Status Code
├── Headers
└── Body
```

### HTTP Status Codes

Status codes tell the client what happened with the request.

They are grouped into categories:

```text
1xx → Informational
2xx → Success
3xx → Redirection
4xx → Client Error
5xx → Server Error
```

Common examples:

```text
200 → OK
201 → Created
301 → Moved Permanently
302 → Found
400 → Bad Request
401 → Unauthorized
403 → Forbidden
404 → Not Found
500 → Internal Server Error
```

Example:

```text
GET /products

        ↓

200 OK

        ↓

Products returned successfully
```

---

## HTTP Headers

**Headers** provide additional information about a request or response.

Example:

```http
Content-Type: application/json
```

This tells the client that the response contains JSON data.

Other common headers include:

```text
Authorization
Content-Type
Accept
Cache-Control
Cookie
User-Agent
```

---

## HTTP Request and Response

This request-response model is one of the fundamental concepts behind web development. The complete communication can be visualized as:

```text
             CLIENT
            Browser
               |
               |
        HTTP Request
               |
               ↓
        ┌─────────────┐
        │   SERVER    │
        └─────────────┘
               |
               |
        HTTP Response
               |
               ↓
             CLIENT
            Browser
```

---

## HTTPS

**HTTPS** stands for **HyperText Transfer Protocol Secure**. It is HTTP communication protected using encryption through **TLS (Transport Layer Security)**.

```text
HTTPS
  ↓
TLS
  ↓
Encrypted communication
```

This helps protect sensitive information such as:

- Passwords
- Authentication tokens
- Payment information
- Personal information

Modern websites should generally use HTTPS. A website using HTTPS commonly begins with:

```text
https://
```
