## Applying CSS

There are 3 ways to implement CSS on a webpage:

1. **Inline CSS** - Where we use the `style` attribute on a HTML tag
2. **Internal CSS** - Where we use the `style` element to store all CSS in one HTML file
3. **External CSS** - Where we store the CSS in a separate file with the extension `.css`

A guide to CSS components:

- the braces `{}` enclose information that the browser will use to style the selected elements
- properties set specific design parameters for the element eg. `color` and `text-decoration`
- colons `:` separate property names from their values
- semi colons `;` terminate each property/value pair 

### How does Inline CSS work?

Inline CSS is where we apply styling to a single element. This however can be come tedious and error prone as we'd have to keep adding a style for every element we want to change. It also mixes presentation with content structure - which is not a good idea.

Inline styles may be shown in production code.

```html
<p>
  Welcome to my website! It's a work in progress as I learn
  <strong style="color: blue; text-decoration: underline;">HTML</strong>
  and <strong>CSS</strong> from a terrific class I'm taking at Launch School. I'm learning a lot! Why don't you join me?
</p>
```

Each name/value pair is separated by a `;` but all of it is in a single pair of quotations. 

Shown above that the second strong element doesn't have the styling that the first one does so we'd have to keep repeating styles. It's very high maintenance and there are more efficient ways to style your HTML.

### How does Internal CSS work?

If you wish to use the CSS on a single page inside the HTML you can use the `style` element which is placed inside the <head> as meta information:

```html
<head>
  <title>Welcome!</title>
  <meta charset="utf-8" />
  
  <style>
    strong {
      color: blue;
      text-decoration: underline;
    }
  </style>
  
</head>
```



### How does external CSS work?

This is when you declare a separate CSS file and identify it as a `stylesheet` using `<link>` tag. Link tags tell the browser where to load the CSS external file on the server. Browsers will make a request for the .css files from the server so it can display the page as it should look.

If you wish you can have multiple css files using one <link> for each css file.

External css files are the preferred way to load styling into your HTML file as it lets you share CSS for multiple pages removing duplication in your code. 

Browsers also cache external files which reduce page load time.

```html
<!DOCTYPE html>
<html lang="en-US">
  <head>
    <title>Welcome!</title>
    <meta charset="utf-8" />
    <link rel="stylesheet" href="my.css" />
  </head>
  <body>
  </body>
</html>
```



### Misc CSS notes

- Most elements by default have a transparent background. By applying a background color property to the body selector, it should become the backdrop for most elements.
- when we apply the `color` property to the `body` everything nested inside it inherits the color. `anchors` are an exception to this rule as browsers add their default styling properties. We can strip them though using a CSS reset.
- by default Mac users have a default san serif font of Helvetica, while Windows users have a defaul san serif font of Arial. To accommodate for both we can add both values to the `font-family` property. If neither font is present on the users OS, we can select the closest san serif font using the `san-serif` value.
- Browsers use a `serif` typeface by default. serif fonts have tails or flat end points. San serif ones do not. [Here's a guide](http://web.mit.edu/jmorzins/www/fonts.html) that will help you select web safe fonts.