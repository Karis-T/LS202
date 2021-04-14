## What are floats?

When we've wanted to place elements side by side we've used `inline` or `inline-block`. This isn't always the best solution eg. using ugly hacks to collapse whitespace between two `inline-block` elements. 

Elements that are **floated** tell the browser to move them **as far left or right as possible**, but leave the remaining space available for additional content.

Because Elements float in their direct container, it limits the browser to how far the floated element can move. 

If two elements are floated in the same direction: 

- their vertical edges (including their margins) will touch provided that they fit on the same row.
- Any whitespace (excluding margins and padding) will collapse

```html
  <div class="outer">
    <div class="primary">
      <p>Main Content</p>
    </div>

    <div class="secondary">
      <p>Sidebar 1</p>
    </div>
  </div>
```

```css
html {
  font-size: 16px;
}

* {
  margin: 0;
  padding: 0;
}

body {
  padding: 0.5rem;
}

p {
  color: black;
  font-family: serif;
  font-size: 1.5rem;
  font-weight: bold;
}

.outer {
  border: 1px solid gray;
  overflow: hidden;
  width: 100%;
}

.primary, .secondary {
  border: 1px solid black;
  box-sizing: border-box;
  text-align: center;
}

.primary {
  background-color: moccasin;
  float: left;
  height: 100px;
  line-height: 100px;
  width: 65%;
}

.secondary {
  background-color: coral;
  float: left;
  height: 75px;
  line-height: 75px;
  width: 30%;
}
```

![Floating Left](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_6/floats-01.png)

If space is needed to be added between the boxes:

- add a `margin-right` to the `primary` div
- or a `margin-left` to the `secondary` div
- or change the `secondary` div to `float: right` 

![Floating Left and Right](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_6/floats-02.png)

If we wish to swap the position of the `primary` and `secondary` div we can do it in the CSS by exchanging where each div floats:

```css
.primary {
  float: right;
}

.secondary {
  float: left;
}
```

![Floating Right and Left](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_6/floats-03.png)



### Floating elements that don't fit

If we were to add extra elements under the sidebar and main content, the extra floats wrap around to the next available spot, but in unexpected ways:

![image-20210410064953148](C:\Users\Karis\AppData\Roaming\Typora\typora-user-images\image-20210410064953148.png)

- sidebar 2 ended up under sidebar 1
- sidebars 5, 6, and 7 stacked up on the right side
- sidebars 4 and 8 didn't float directly under sidebar 2 as expected.

Because of these crazy behavior most developers try to keep floats simple:

- make sure all floats in a group have the **same height and direction** - either left or right and they *will* wrap logically
- You can mix left and right floats with predictable results, provided that **all the heights are the same**
- consider working with fixed height and width containers
- Or better still use `flex`,  `grid` or a Frameworks package.
- when you float an element it **uses as much space as it needs to display the content**. To keep the element floated but extend the width use `width: 100%`

```css
#floated {
  width: 20%;
}

main > p {
  /* clear: both; */
  margin-left: 20%;
}
```

This code works but it can become unstable if you added a fixed height to `main > p` and it isn't enough to contain the text, it will overflow. If you added `overflow: hidden` the overflow text gets clipped. if you add `overflow: auto` you could scroll `main > p`