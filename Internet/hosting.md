# What Is Hosting?

**Web hosting** is a service that provides a place for a website or web application to run and be accessed over the Internet. A website consists of resources such as:

```text
HTML
CSS
JavaScript
Images
Fonts
Other Files
```

These files need to be stored and served from a computer connected to the Internet. That computer is commonly called a **server**.

```text
Website Files
     |
     ↓
   Server
     |
     ↓
  Internet
     |
     ↓
   Users
```

## Why Do We Need Hosting?

Suppose we build a website on our computer:

```text
my-project/
├── index.html
├── style.css
└── script.js
```

The files exist on our computer, but other people cannot automatically access them through the Internet. Hosting places the website on infrastructure that can receive requests from users.

```text
Your Computer
     |
     | Upload / Deploy
     ↓
Hosting Server
     |
     ↓
Internet
     |
     ↓
Users
```

---

## Types of Hosting

Different hosting approaches exist depending on the application's requirements.

### Shared Hosting

Multiple websites share resources on the same server. It is commonly used for smaller websites.

```text
Server
│
├── Website A
├── Website B
├── Website C
└── Website D
```

### VPS

**VPS** stands for **Virtual Private Server**. A physical server is divided into virtual servers. Each VPS provides more control than typical shared hosting.

```text
Physical Server
│
├── VPS A
├── VPS B
├── VPS C
└── VPS D
```

### Dedicated Server

A dedicated server provides an entire physical server for a particular customer or application.

```text
Physical Server
       |
       ↓
   One Customer
```

### Cloud Hosting

Cloud hosting uses distributed infrastructure instead of relying on one physical machine. Modern applications can run across multiple servers and locations.

```text
             Cloud
          /    |    \
      Server Server Server
         \     |     /
          \    |    /
           Application
```

Cloud platforms can also provide services such as:

- Databases
- Storage
- Serverless functions
- Networking
- Authentication
- Monitoring

---

## Static and Dynamic Hosting

### Static Website

A static website can serve pre-built files directly.

```text
Browser
   ↓
Web Server
   ↓
index.html
```

### Dynamic Website

A dynamic application may need backend code and databases.

```text
Browser
   ↓
Backend Server
   ↓
Application Logic
   ↓
Database
   ↓
Response
   ↓
Browser
```

This is common for applications involving:

- Authentication
- User accounts
- Payments
- Orders
- Databases
- Personalized content
