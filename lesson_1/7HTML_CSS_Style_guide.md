## HTML Style

1. Don't cram more than 2 elements on a single line.

```html
<!-- Legal but hard to read -->
<nav><ul><li>Home</li><li>Sign Up</li><li>Log In</li><li>Log Out</li></ul></nav>

<!-- Acceptable, but a bit hard to read -->
<li><a href="home.html">Home</a></li>
<a href="home.html"><img src="home.gif" /></a>
```

1. Be consistent with your indentation. (use 2 or 4 or hard tabs)
2. Don't indent the `HTML` tag
3. Use `/>` with self closing-tags as it improves readability and helps support XML or older versions of HTML. (and be consistent)
4. Using flex or grid place the most significant content blocks at the top of the file and the least important ones at the bottom.

## CSS Style

1. Don't put more than 1 property on the same line. Fallbacks are the exception -(adding extra properties on the same line to support older and newer browsers)

```css
/* Legal but hard to read and maintain */
p {
  background-color: yellow; border: 3px dashed #888; color: red;
}

/*fallbacks are the exception*/
p {
  background-color: yellow;
  color: red;
  width: 50%; width: 50vw; /* fallback to 50% if 50vw not recognized */
}
```

2. Be consistent with your indentation. (use 2 or 4 or hard tabs)
3. put the opening `{` on the same line as the selector. Put the closing `}` on a line at the end of the last property

```css
p {
  color: red;
}
```

4. include a space between the property and the value

```css
p {
  background-color: orange;
  border: 3px solid green;
  color: black;
}
```

5. don't include a space before the semicolon `;`
6. be aware of overriding properties. Typically order the properties alphabetically but sometimes it conflicts. 

```css
p {
    margin: 25px;
    margin-right: 10px;
    /* Partial override: `margin: 25px 10px 25px 25px;` */
}

blockquote {
    margin-right: 10px;
    margin: 25px;
    /* Complete override: `margin: 25px;` */
}
```

7. group selectors by function (all the articles together or the paragraphs together). If that doesn't work then look at the cascade and specificity.  Linters can help with potential css problems and save a lot of time.
8. Stick with class selectors and avoid type and ID selectors to reduce weight issues. 