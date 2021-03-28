## Box-Sizing Takeaways

- Microsoft always ran 'quirks' mode - what we call `border-box` today. It was originally a bug which it made it impossible for developers to get a consistent look amongst browsers
- The bug was fixed by Microsoft and created 'quirks' mode for backward compatibility but most developers actually like a prefer the 'quirks' mode.
- don't use the `padding-box` setting - it's deprecated
- `content-box` is the default for all modern browsers - `width` and `height` properties define the **content area** of the box
- `border-box` uses the `width` and `height` properties as the **final dimensions** of the box (excluding margins)
- `border-box` is the better choice as it cuts down the math a front end developer needs to do.
- to reset the CSS and add border-box anywhere, use the following CSS:
- modern pseudo elements use, users double colon.

```css
html {
  box-sizing: border-box;
}

*, *::before, *::after {
  box-sizing: inherit;
}
```

## Practice Problems: The Box Model

- When calculating `content-box` elements, you must **ADD:**
  - `padding` on either side
  - `border` on either side
  - `margin` on either side
  - to the original `width` (this works with `block` and `inline-block`)

- When calculating `border-box` elements, you must **IGNORE:**
  - `padding` on either side
  - `border` on either side
  - keep the original `width` (this works with `block` and `inline-block`)

### Inline elements

- For `inline` elements, the only way to calculate the amount needed to contain the element, is to know the actual width and height of the content.
- top and bottom `margins` are **ignored** with `inline` elements
- top and bottom padding borders may intersect with the content above and below `inline` elements
- `width` property doesn't affect `inline` elements and is determined by the actual width of the content in the browser.

### neighboring elements

- if any neighboring element is a `block` element regardless of size, it will take up the whole width, making others drop to a new line
- if there are neighboring `inline` and `inline-block` elements as long as they fit in the width of the container, they will sit side by side
- to change neighboring `block` elements so they sit side by side, set their `display` to `inline-block` and `box-sizing` to `border-box`
- if you put `block` elements on two different lines in HTML, the browser considers this as whitespace which is reduced to a single space character and it is used as content between the elements. This problem usually occurs with `inline-block` elements. To eliminate whitespace you can place the two tags next to each other or you can remove the white space or make it invisible.