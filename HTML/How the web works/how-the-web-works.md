# How the Web Works

What actually happens when you type a website address into your browser? A simplified version looks like this:

```
              You
               │
               │ Enter URL
               ▼
          ┌─────────┐
          │ Browser │
          └────┬────┘
               │
               │ Request
               ▼
          ┌─────────┐
          │ Server  │
          └────┬────┘
               │
               │ Response
               ▼
          ┌─────────┐
          │ Browser │
          └────┬────┘
               │
               ▼
          Web Page
```

There are several concepts involved in this process:

```
How the Web Works
│
├── HTTP
├── Domain Names
├── Hosting
├── DNS
├── Browsers
└── SEO
```

---

# 1. What is HTTP?

**HTTP** stands for **HyperText Transfer Protocol** HTTP is a protocol used for communication between a **client** and a **server** on the web. In simpler terms:

> HTTP defines how requests and responses are exchanged between web clients and servers.

```
CLIENT                              SERVER

┌─────────────┐                  ┌─────────────┐
│             │                  │             │
│   Browser   │                  │   Server    │
│             │                  │             │
└──────┬──────┘                  └──────▲──────┘
       │                                │
       │       HTTP Request             │
       ├───────────────────────────────►│
       │                                │
       │       HTTP Response            │
       │◄───────────────────────────────┤
       │                                │
       ▼                                │
   Display page                         │
```

## HTTP Request

When your browser wants something from a server, it sends an **HTTP request**.

For example:

```
GET /index.html HTTP/1.1
Host: example.com
```

## HTTP Response

The server processes the request and sends back an **HTTP response**.

For example:

```
HTTP/1.1 200 OK
Content-Type: text/html
```

The response can contain the requested HTML.

```
<!DOCTYPE html>
<html>
    <body>
        <h1>Hello World</h1>
    </body>
</html>
```

The browser then processes the response and renders the page.

---

## HTTP Methods

HTTP defines different methods for communicating intent.

Some common ones are:

| Method   | Common purpose        |
| -------- | --------------------- |
| `GET`    | Retrieve data         |
| `POST`   | Send/create data      |
| `PUT`    | Replace data          |
| `PATCH`  | Partially update data |
| `DELETE` | Delete data           |

> **HTTP is the communication protocol that allows clients and servers to exchange information on the web.**

---

# 2. Domain Names

A **domain name** is the human-readable address used to access a website.

Examples:

```
google.com
github.com
roadmap.sh
example.com
```

Computers communicate using IP addresses, which look something like:

```
142.250.72.14
```

Remembering IP addresses for every website would be inconvenient. Instead, we use domain names.

```
Human
  │
  │ types
  ▼
google.com
  │
  │ translated to
  ▼
142.250.72.14
  │
  ▼
Server
```

So a domain name acts as a **human-friendly name for a network destination**.

---

## Domain name structure

Consider:

```
www.example.com
```

It can be broken down into:

```
www      . example . com
 │           │        │
 │           │        └── Top-Level Domain (TLD)
 │           │
 │           └── Domain name
 │
 └── Subdomain
```

---

# 3. Hosting

A website needs somewhere to **live** so that people can access it over the Internet. This is where **web hosting** comes in.

> Hosting is the service of providing the infrastructure needed to store and serve a website or web application. A hosting server provides an environment.

```
             INTERNET
                 │
       ┌─────────┴─────────┐
       │                   │
       ▼                   ▼
   User A                User B
   Browser               Browser
       │                   │
       └─────────┬─────────┘
                 │
                 ▼
          ┌─────────────┐
          │   Hosting   │
          │   Server    │
          ├─────────────┤
          │ index.html  │
          │ style.css   │
          │ script.js   │
          │ images/     │
          └─────────────┘
```

---

# 4. DNS

**DNS** stands for **Domain Name System**. DNS translates human-readable domain names into IP addresses that computers can use to locate servers.

For example:

```
example.com
     │
     │ DNS lookup
     ▼
93.184.216.34
     │
     ▼
Server
```

Without DNS, we would frequently need to remember IP addresses instead of domain names.
**DNS as the Internet's phonebook**

## A simplified website request

```
1. Browser receives:
       example.com

2. Browser needs the server's IP.

3. DNS lookup:
       example.com
            ↓
       IP address

4. Browser connects to the server.

5. Browser sends an HTTP request.

6. Server sends a response.

7. Browser processes the response.

8. Page is displayed.
```

---

# 5. Browsers

A **web browser** is software used to access and interact with resources on the web. Examples include:

- Google Chrome
- Mozilla Firefox
- Microsoft Edge
- Safari

A browser does much more than simply "display websites." It:

1.  Sends requests to servers.
2.  Receives resources.
3.  Parses HTML.
4.  Parses CSS.
5.  Executes JavaScript.
6.  Builds internal representations of the page.
7.  Calculates layout.
8.  Renders the result on the screen.

A simplified picture:

```
             Web Server
                 │
                 │
        HTML / CSS / JS
                 │
                 ▼
        ┌────────────────┐
        │    Browser     │
        ├────────────────┤
        │ Parse HTML     │
        │ Parse CSS      │
        │ Run JavaScript │
        │ Calculate      │
        │ layout         │
        │ Render         │
        └───────┬────────┘
                │
                ▼
          Visible webpage
```

---

# 6. What is SEO?

**SEO** stands for **Search Engine Optimization**

> SEO is the practice of improving a website so that search engines can better **discover, understand, and present** its content to users.

SEO can involve:

- Content quality
- Page structure
- Semantic HTML
- Page performance
- Mobile friendliness
- Links
- Metadata
- Accessibility
- Search engine crawling
- Website authority

---

# 🔄 Putting Everything Together

```
                     YOU
                      │
                      │ Enter URL
                      ▼
              ┌─────────────┐
              │   Browser   │
              └──────┬──────┘
                     │
                     │
                     ▼
              ┌─────────────┐
              │     DNS     │
              └──────┬──────┘
                     │
                     │ Finds IP address
                     ▼
              ┌─────────────┐
              │   Server    │
              │  / Hosting  │
              └──────┬──────┘
                     │
                     │ HTTP Response
                     ▼
              ┌─────────────┐
              │   Browser   │
              └──────┬──────┘
                     │
             ┌───────┼────────┐
             │       │        │
             ▼       ▼        ▼
            HTML     CSS     JavaScript
             │       │        │
             ▼       ▼        ▼
          Structure Style   Behaviour
             │       │        │
             └───────┼────────┘
                     │
                     ▼
              Rendered webpage
                     │
                     ▼
                 👤 User
```

And somewhere in this picture, SEO helps search engines discover and understand the content of your website.
