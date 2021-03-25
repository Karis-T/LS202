## Creating a HTML Skeleton

###### What is the HTML skeleton / HTML scaffold?

```html
<html lang="en">
<head>
  <title>Page Title Goes Here</title>
  <meta charset="utf-8" />
</head>
<body>
</body>
</html>
```

It's a template of the minimum amount HTML you need to begin creating a page. This file is typically used again and again instead of writing it out each time. This file is known as a HTML skeleton, HTML scaffold or a boilerplate.

### How do we create a HTML Skeleton?

You need the DTD, html, head and body as required parts that makeup a HTML page. But you can omit them if you want and the browser should be able to interpret it. It's may however cause problems across different browsers so its not recommended.

###### What is `<!DOCTYPE html>`? 

Document Type Definition / DTD / DOCTYPE is the **very first message at the top of the page**. It indicates what markup language is going to be used - in this case HTML5, which is the primary HTML language written, unless you're writing for older HTML or other application's such as XML or XHTML. Use uppercase to declare the `!DOCTYPE`

###### What is `html` element?

The `html` element encloses the whole HTML document. It's `lang="en"` attribute indicates the language for the webpage - English. All contents within a HTML page, including its meta information, should be contained with the `html` tags.

###### What is `head` element?

The head typically contains addition meta information about the webpage that the browser should know. Things like the < title > that displays the name of the page in the tab, or the < meta charset="utf-8" >, which is the standard character encoding most web site use.

<div style="border: 1px solid gray; padding: 1% 4% 2% 4%;">
<h6>Self closing tags</h6>  
<p>tags like < meta > are considered to be self-closing. This means they don't have a closing tag. Other terms for self-closing are "self-contained element", "empty element" or "void element".</p>
</div>

###### What is the `body` element?

The `body` is the only content that's rendered by the browser. Editors have a shortcut that allows you to view the html in a browser context.

#### How do we use indentation?

Use 2 spaces for indenting html documents to make the document easier to read, organize and edit. Typically though The DTD, `html` `head` and `body` indentation can be omitted.