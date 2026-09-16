# Internet

The **Internet** is a global network of interconnected computers and devices that communicate with each other using standardized protocols.
It allows devices around the world to exchange information such as:

- Web pages
- Images
- Videos
- Files
- Emails
- API data
- Messages

## How Does the Internet Work?

The Internet works by connecting millions of devices through networks and allowing them to communicate using standardized protocols. When we visit a website, our browser does not magically retrieve the website. Several steps happen behind the scenes.

For example, suppose we enter:

```text
https://example.com
```

The general process looks like this:

```text
       User
        |
        ↓
     Browser
        |
        ↓
       DNS
        |
        ↓
Find the server's IP address
        |
        ↓
   HTTP / HTTPS
        |
        ↓
     Internet
        |
        ↓
     Web Server
        |
        ↓
     Response
        |
        ↓
     Browser
        |
        ↓
   Render Website
```

**Step 1 — Enter a URL**

When we enter a website address into the browser, the browser needs to determine where that website is located.

**Step 2 — Find the IP Address**

Computers communicate using **IP addresses**, but humans usually use domain names because they are easier to remember. The system responsible for translating domain names into IP addresses is called **DNS (Domain Name System)**.

Example:

```text
example.com
     ↓
IP address
     ↓
93.184.216.34
```

**Step 3 — Establish a Connection**

The browser communicates with the server associated with that IP address.

For HTTPS connections, additional security mechanisms are used to establish an encrypted connection.

**Step 4 — Send an HTTP Request**

The request tells the server what the browser wants. The browser sends an **HTTP request** to the server.

Example:

```text
GET / HTTP/1.1
Host: example.com
```

**Step 5 — Server Processes the Request**

The server receives the request and determines what response should be returned.

The server may:

- Read files
- Execute backend code
- Query a database
- Call another API
- Perform authentication
- Generate data

**Step 6 — Server Sends a Response**

The server sends an HTTP response back to the browser. A simplified response might look like:

```text
HTTP/1.1 200 OK

<html>
    <body>
        <h1>Hello!</h1>
    </body>
</html>
```

**Step 7 — Browser Renders the Page**

The browser receives the response and processes the resources needed to display the website.

For a typical website:

```text
HTML
 ↓
Page Structure

CSS
 ↓
Styling

JavaScript
 ↓
Behavior / Interactivity
```

The browser parses these resources and constructs the visual page we see.

---

### Client and Server

The Internet commonly involves communication between **clients** and **servers**.

#### Client

A **client** is a device or application that requests a service or resource.

Examples:

- Web browser
- Mobile application
- Desktop application

#### Server

A **server** is a computer or software system that receives requests and provides resources or services.

Example:

```text
Client                         Server

Browser  ───── Request ─────→  Web Server
Browser  ←──── Response ─────  Web Server
```

A single device can sometimes act as both a client and a server depending on what it is doing.
