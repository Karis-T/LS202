## How do I contain a float?

```html
<div id="container">
  <div id="primary">
    <h1>Main Content</h1>
  </div>

  <div id="secondary">
    <h3>Sidebar Content</h3>
  </div>
</div>
```

```css
#container {
  background-color: #e0e0e0;
  box-sizing: border-box;
  margin: 0 auto;
  padding: 20px;
  width: 780px;
}

#primary {
  float: left;
  width: 500px;
  background-color: yellow;
}

#secondary {
  float: right;
  width: 200px;
  background-color: yellow;
}
```

![Uncontained floats](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_6/containing-floats-01.png)

Right now it looks like the yellow div containers are hanging halfway outside the gray containers. This is a typical float issue where 

- the browser removes floated elements from the normal document flow
- This means the container no longer contains the elements.
- The browser therefore cannot calculate the containers height and isn't able to render the container properly.
- Floated elements can overwrite other content. To fix this we can: 
  - add an overflow option to the elements container or
  - wrap the container in a **clearfix**

The simplest way to clear a floated element is apply to the container:

- `overflow: hidden`
- `overflow: auto`

The container will expand and wrap the floated elements

```css
#container {
  overflow: hidden;
}
```

![Floats contained with overflow](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_6/containing-floats-02.png)

### What is `overflow`?

Overflow makes the container envelop both `divs`. Be cautious to use `overflow` as it can cause two potentially unwanted situations:

- `overflow: hidden` can cut off / clip content that exceeds the available space if the container has fixed height / width
- `overflow: auto` adds scroll bars - based on browser behavior.
- use the `clear` fix approach to solve either problem

Overflow works because it creates a **block formatting context** where everything inside the container is formatted as a block.

- adding `overflow: hidden` to the *last floated element in a row* and removing any `float` or `width` properties allows it to take up the remaining space in a row
- This technique is useful when you want your **last element to takup the leftover space within a variable layout** 

### What is the `clear` fix?

**clearfix** is a pattern that allows containers not to lose its floated elements by wrapping its content.

```css
#container::after {
  clear: both;
  content: "";
  display: block;
}
```

- The `::after` pseudo element works as our clearfix:
  - It creates a child element at the end of the container `display: block` on its own line
  - `content: ""` sets the content of the child element to an empty string (rendering the clearfix invisible)
  - `clear: both` forces the invisible child directly below the floated content

The final result is similar to `overflow` and the container can see the clearfix so it stretches itself to enclose the clearfix and floated content

clearfix values are either `right` `left` or `both` which refers to which floated elements it will clear. You should however use `clear: both`

`::after` always places content after the content in its container. Always use double colons with pseudo elements. The standard allows you single, but it may not always work. `::after` and `::before` are the most useful out of the dozen pseudo elements with half being [experimental](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements). 

```html
<p>Hello</p>
```

```css
p::before {
  content: "+- ";
  color: red;
}

p::after {
  content: " -+";
  color: blue;
}
```

![before and after](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_6/before-and-after.png)