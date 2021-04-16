## CSS Resets

When you use CSS to style documents, the browser applies its own default styling to HTML elements. While this can be handy with HTML alone, its unhelpful when we add CSS to the mix. This is why we use CSS resets - to remove and override browser styling defaults and work with a clean slate. That way there's no unexpected styling from browser to browser and its should appear the same.

These are the most common CSS resets:

- [Eric Meyer's reset](http://meyerweb.com/eric/tools/css/reset/)
- [Normalize.css](http://necolas.github.io/normalize.css/)
- [Tantek Celik's whitespace reset](http://cssreset.com/scripts/undohtml-css-tantek-celik/)

Resets are usually customized. Here's LS's version based on Tantek's reset:

```css
/*
----------------------------------------
Tantek Celik's Whitespace Reset
     Author:    Tantek Celik, Shane Riley
    Version:    (CC) 2010 Some Rights Reserved - http://creativecommons.org/licenses/by/2.0
Description:  Resets default styling of browsers to a common base
----------------------------------------
*/

ul, ol { list-style: none; }
h1, h2, h3, h4, h5, h6, pre, code { font-size: 1em; }
ul, ol, li, h1, h2, h3, h4, h5, h6, pre, form, body, html, p, blockquote,
fieldset, input, dl, dt, dd, figure, figcaption {
  margin: 0;
  padding: 0;
}
a img, :link img, :visited img, fieldset { border: none; }
address { font-style: normal; }
header, section, article, nav, footer, hgroup, details, summary, figure, main {
  display: block;
}
mark {
  color: inherit;
  background-color: transparent;
}
abbr { border: none; }
summary::-webkit-details-marker { display: none; }
```

This reset:

- removes the bullets on ordered and unordered lists.
- sets all headings and a few other items to use the same font size.
- sets the padding and margins on most `block` elements to 0.
- removes the border that surrounds images inside links on older browsers.
- removes the border on `fieldset`.
- converts `address` elements to look like regular text.
- sets newer HTML elements to `display: block`, in case the user has an old browser that defaults to `inline`.
- removes garish colors from the `mark` element.
- removes the bottom border from `abbr` elements.
- removes the toggle marker from the `summary` element.