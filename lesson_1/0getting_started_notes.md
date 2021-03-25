## Getting Started

read the first part of the tutorial for an introduction into the vocab and essential concepts of HTML and CSS. 

### What do you need to do before getting started?

What you need to takeaway from the tutorials:
- The vocab
- The HTML / CSS syntax
- HTML elements, CSS selectors and properties mentioned
- `class` and `id` attributes and their corresponding selectors `.class-name`, `#id-name` 
- and of less importance but still worth studying:
  - how to write HTML and CSS comments
  - difference between `<header>`, `<head>`, `<h1>` to `<h6>` 
  - relative and absolute paths
  - CSS cascade and specificity

use `mdn` to lookup various HTML tags and CSS properties

most topics will be discussed later so don't waste time trying to memorize everything from the tutorial. 

### What are the tutorials and how do I read them?

read the first 3 sections of Shay Howe's extensive HTML / CSS tutorial which covers most concepts.
- [Build your first webpage](https://learn.shayhowe.com/html-css/building-your-first-web-page/) - An introduction to common tags, rules and HTML / CSS vocab
- [Get to know HTML](https://learn.shayhowe.com/html-css/getting-to-know-html/) - Discusses Semantics, headings, paragraphs, HTML based styling, URL and hyperlinks and looks at the general structure of a HTML document. 
- [Get to know CSS](https://learn.shayhowe.com/html-css/getting-to-know-css/) - introduces CSS cascade, specificity, selectors and various properties 

### What are the afterthoughts?

Although used interchangeably, there's a distinct difference between HTML elements and tags:

- HTML tags:
  - begin with `<` and end with  `>` and has the element name inside the angle brackets
  - There are 3 types of tags: opening tags `<p>`, closing tags `</p>` and self closing tags `<img />` (most tags aren't self-closing)
- HTML elements either:
  - include a self-closing tag
  - OR an opening and closing tag and everything between the two. The content may also contain nested elements.

LS may refer to elements with or without angle brackets out of convenience.

 

```html
<a href="another_page.html">Next page</a>
<a href='another_page.html'>Next page</a>
```

`href` is an **attribute** of the `<a>` tag that has the value of `another_page.html`. feel free to use double or single quotes. Even though you can don't omit quotes. Where possible use double quotes as recommended by most style guides.

**Boolean attributes** require no `=` nor values attached to it.

some attributes like `class` are global and can be used anywhere but typically most HTML elements / tags contain none or more attributes

browsers ignore attributes which makes them difficult to debug.

### What is the rest of the tutorial?

Complete the [Advanced HTML and CSS Tutorial](https://learn.shayhowe.com/advanced-html-css/) after you've completed this course. It doesn't fit into the structure of this course but if you want to learn more check it out.

