# `<meta>`

The `<meta>` element provides metadata about the HTML document. It doesn't contain visible page content and doesn't require a closing tag.

"Metadata" simply means data about data.

## Character Encoding

This specifies the document's character encoding. Character encoding defines how those characters are represented digitally.

What is character encoding?

Computers store information as numbers/bits, but text contains characters such as:

```
A B C
1 2 3
বাংলা
中文
日本語
é
©
😊
```

```html
<head>
  <meta charset="UTF-8" />
</head>
```

This helps the browser correctly interpret the characters in documents.

## The Viewport Meta Tag

Websites are viewed on many different devices like, desktop, tablet, and phone. The viewport is essentially the **area of the webpage that is visible to the user**. This meta declaration tells the browser how to treat the page's viewport on different devices.

```
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
                               |                    |
                               |                    |
                               Make the viewport    initial zoom level
                               width correspond
                               to the device's
                               screen width.
```

## Other `<meta>` Information

The `<meta>` element can provide different kinds of metadata. `<meta />` isn't one specific piece of information. It is a general element used to provide metadata in different forms.

````html
<meta name="description" content="A personal portfolio website." />
```

This provides a description of the page. Another example:


```html
<meta name="author" content="Mahmuda" />
```

This provides author information.