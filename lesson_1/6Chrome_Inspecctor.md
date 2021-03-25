### What is the Chrome Inspector and Developer Tools?

The chrome inspector tool is an advanced way to look into other websites and find out what elements, selectors, properties and styles they used to create their look. You can click on individual elements and it displays all the information about how it was structured in HTML and CSS.

The chrome inspector tool is a part of a larger set of chrome tools called the **Developer tools**. Since they change often the documentation can be referred to [here](https://developers.google.com/web/tools/chrome-devtools/), particularly the [Viewing and Changing the DOM](https://developers.google.com/web/tools/chrome-devtools/dom/) section. 

The important things to understand about the developer tools is:

- the elements tab with regard to the HTML styles and Computer Panels
- How to modify styles dynamically so you can see the effects on the page live.
- You can think of DOM Nodes as another word for HTML elements.

Use the developer tools for debugging and experimenting.

If you wish to reconfigure the Development tools placement in your browser refer to the [UI Documentation](https://developers.google.com/web/tools/chrome-devtools/ui)

### HTML vs The DOM

1. When a browser parses a HTML page it creates a tree of objects like this:

```
html
  head
    title
  body
    h1
    p
    script
```

2. This tree of objects called nodes is called the DOM (Document Object Model) and it represents the page's content. Right now its similar to the HTML
3. However if we run the DOM's `script` it could alter the DOM's nodes like so:

```
html
  head
    title
  body
    p
    script
    p
```

Now the page's HTML is now different than its DOM. 

**The HTML represents the initial page and the DOM represents the current page content.** When the script adds removes or edits the nodes, the DOM becomes different to the HTML.