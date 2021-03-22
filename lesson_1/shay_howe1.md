## Building Your First Webpage

### What is the difference between HTML and CSS?

- **Hypertext Markup Language or HTML** gives structure and meaning to content such as paragraphs, headings and images.
- **Cascading Style Sheets or CSS** is a presentation language that styles the appearance of the content.
- As a rule the two should be independent of one another and not be written inside each other documents.

### What are HTML elements, tags and attributes?

- **Elements**:

  - elements are designated objects that define HTML page content and structure. They are comprised of a less than greater than symbol with an element name
  - common elements are `<p>`, `<h1>` to `<h6>`, `<a>`, `<div>`, `<span>`, `<strong>` and `<em>`

  ```html
  <a href="http://shayhowe.com/">Shay Howe</a>
  ```

- **Tags**:

  - The less than greater than symbols surrounding an element name is a tag. Most tags have an opening and closing tag which mark the beginning and end of an element. 

  ```html
  <a>...</a>
  ```

- **Attributes:**

  - properties that provide additional information about an element. They follow an element's name in the opening tag and are comprised of name value pairs separated by an equals sign (unless they are boolean).

  ```html
  <a href="http://shayhowe.com/">
  ```

### How do I structure a webpage?

- HTML has a required structure including the declaration <!DOCTYPE html> and elements <html>, <head> and <body>
-  The declaration <!DOCTYPE html> indicates which version of HTML you are using
- following the declaration comes the <html> element which indicates the beginning of the html document.
- inside the <html> comes the <head> element which contains any additional metadata for the page (such character encoding <meta charset="utf-8"> as the webpage title and links to external files). Information within the <head> of the page isn't displayed.
- all visible content is contained in the <body> of the webpage.
- Make sure to indent nested elements
- Validate your code often with W3C tools to support cross browser compatibility and encourage best practices.

```html
<html>
  <head>
    <meta charset="utf-8">
    <title>Hello World</title>      
  </head>
  <body>
    <h1>Hello World</h1>
    <p>This is a webpage.</p>
  </body>
</html>
```

- Not all elements have opening and closing tags. Some are considered self closing which means they get their behavior and attributes from a single tag. Here are the common ones used: `<br>` `<embed>` `<hr>` `<img>` `<input>` `<link>` `<meta>` `<param>` `<source>` `<wbr>`

### What are CSS selectors, properties and values?

Here are the common CSS terms you need to be familiar with:

- **selectors**: 

  - Selectors target HTML elements and assigns styling to them (eg. color, size). We can qualify as much or as little as we want: from styling just 1 paragraph on a page to all the paragraphs on a page.

  - Selectors target either attributes `id` / `class` or elements `<h1>` / `<p>` for styling.

  - CSS opens and closes each selector with curly brackets 

    ```css
    p {
    }
    ```

  1. Type Selectors

     - target elements by their type: eg if we wanted to target divisor elements, use a type `div` selector:

     ```css
     /* css */
     div { 
     	color: blue;
     }
     ```

     ```html
     <!---html--->
     <div>
       all div text should now be styled blue
     </div>
     ```

  2. Class Selectors

     - Select elements based on the `class` attribute value. It's more specific than type selectors and targets a specific group of elements rather than all the elements of a type. Classes are prefixed with a `.` in css

     ```css
     /* css */
     .awsome {
       color: red;
     }
     ```

     ```html
     <!---html--->
     <div class="awesome">...</div>
     <p class="awesome">...</p>
     ```

  3. ID Selectors

     - ID selectors are even more specific than class selectors, targeting only one element at a time. Like class selectors, id selectors selects elements based on the `id` attribute value. Id's are prefixed with `#` in css.  a single`id` can only be used once per page and should therefore be used for significant elements.

     ```css
     /* css */
     #signature { 
       ... 
     }
     ```

     ```html
     <!---html--->
     <div id="signature">...</div>
     ```

  - There are also more [advanced selectors](https://learn.shayhowe.com/advanced-html-css/complex-selectors/) available, but the 3 above are the most common.

- **properties**

  - Properties are all the styles that we can apply to a targeted element. They sit between the curly brackets, each followed by a `:` and are terminated with a `;`

  ```css
  p {
    color: ;
    font-size: ;
  }
  ```

- **values**

  - Values determine the behavior of each property sitting between the `:` and `;`

  ```css
  p {
    color: orange;
    font-size: 16px;
  }
  ```

- in summary, the css rule set starts with a selector followed by curly brackets. Inside the curly brackets are property / value pair declarations which as a common practice should be indented.  

![CSS Syntax Outline](https://learn.shayhowe.com/assets/images/courses/html-css/building-your-first-web-page/css-syntax-outline.png)

### How do I reference CSS in HTML?

- In order to have the CSS style sheet talk to your HTML page, you should have all styles contained within an external CSS style sheet. It then needs to be referenced within the `<head>` of the HTML. Having one style sheet allows us to have the same style and make quick changes across the entire site.

- internal and inline styles are less conventional and make it difficult to update websites

- to create a css file it must have the file extension `.css` and needs to be located in the same or subfolder of the HTML file

- inside the `<head>` of a HTML page, use the `<link>` element followed by the `rel` attribute with `stylesheet` as its value. Also include the `href` of the location of the `.css` file.

  ```html
  <head>
    <link rel="stylesheet" href="main.css">
  </head>
  ```

### Why are CSS resets valuable?

- CSS resets helps aid in cross browser compatibility
- Browsers like to impose their own preferred styles that haven't been declared in the CSS file. They can be overridden with CSS presets.
- A CSS reset is when we remove any preset HTML element styling in favor of one unified style. This works as a common baseline for all browsers and must be placed at the top of the page,  since CSS is parsed from top to bottom. Sizing, margins, padding and any other additional styling is stripped away.
- [Eric Meyer's reset](http://meyerweb.com/eric/tools/css/reset/) is a popular CSS reset
- website browsers render webpages in different ways. While the page doesn't have to be EXACTLY the same, they should be close enough. Based on the needs of your website you can test for Cross browser Compatibility.