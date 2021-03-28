## Box sizing

`box-sizing` **property** makes designing CSS layouts more intuitive for developers.

### What should I know about Box Model History?

the box model when it was first created used this formula to calculate its rendered dimensions:

```
height + padding + border = final rendered height of element's box
width + padding + border = final rendered width of element's box
```

This doesn't make sense because as soon as you add border and padding, the final width and height of the box change.

Internet Explorer used what is called today as *"quirks mode"* :

```
width = final rendered width of box including padding + border
height = final rendered height of box including padding + border
```

this means that `border` and `padding` were moved inside of the elements box and *editing the `width` and `height` of the box* instead of expanding it.

![img](https://i2.wp.com/css-tricks.com/wp-content/uploads/2010/09/widthbox.png?resize=367%2C604)

1. top: `content-box` *adds* padding and border to set width and height and extends past the set width and height boundaries 
2. bottom: `border-box` *subtracts* padding and border from set width and height to meet the set width and height boundaries

Previously you had to do a bit of math to factor in border and padding, but it isn't very applicable anymore because we don't use absolute measurements anymore due to *responsive design.*

### what does `box-sizing` today look like?

`box-sizing` was introduced in CSS3 as a property that accommodates 3 modes: 

- `content-box` (default used by browsers)
- `padding-box`(deprecated)
- `border-box`(quirky, intuitive way used as a reset style for responsive design)

### What are some of the box-sizing reset methods?

#### What is the old border-box reset method?

```css
* {
  box-sizing: border-box;
}
/* this is good but leaves out pesudo elements,has unexpected results */
```

#### What is the universal box-sizing reset and why is it better?

```css
*, *:before, *:after {
  box-sizing: border-box;
}
/* supports pseudo elements but '*' doesn't allow for content-box */
```

#### Why is the universal box-sizing with inheritance the best?

```css
html {
  box-sizing: border-box;
}
*, *:before, *:after {
  box-sizing: inherit;
}
/* now supports content-box using inhertance*/
```

```html
<div class="component"> <!-- I'm content-box -->
  <header> <!-- I'm border-box still! -->
  </header>
</div>
```

using inheritance helps prevent the above from happening and preserves changes all the way through. It isn't a huge thing but its a best practice.

### What are some known issues with box sizing?

While `border-box` is supported by current versions of all browsers today there are older versions of IE 8 and below that issues or don't support it at all.