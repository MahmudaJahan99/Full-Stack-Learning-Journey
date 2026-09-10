# <!DOCTYPE>

This is called the **DOCTYPE declaration**. It tells the browser which HTML standard the document is intended to follow.

```html
<!DOCTYPE html>
```

Technically <!DOCTYPE> is not an HTML tag. It is a **declaration**, not an HTML element. That's why it doesn't look like the other HTML elements. It also doesn't have a closing tag.

## Why do we need it?

The DOCTYPE declaration helps the browser **render the document using standards mode** rather than an older compatibility mode. Historically, HTML doctypes were much more complicated.

## Where does it go?

It should be the first thing in the HTML document:

`<!DOCTYPE html>` tells the browser to interpret the document as modern HTML and use standards mode. It doesn't create an element and it doesn't appear on the webpage.