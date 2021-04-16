## What is Flex?

Flexbox layout (or more specifically the Flexible Box Module) was designed to create more intuitive efficient layouts. It does this by distributing space of items inside a container particularly when the size of the item is unknown or dynamic.

Flexbox gives the developers the advantage of being able to manipulate the items inside a container by width, height, order etc. in order to best fill any remaining space. This is particularly handy when a webpage needs to accommodate many screen sizes and must be shrunk for mobile devices. Unlike plain css/html its also direction agnostic

`Flex` is best suited to small-scale layouts and components of an application. Whereas `grid` is suited to larger scale layout design.

### Basics and Terminology:

Flexbox is more than just a property, its an entire module with a set of properties. With it comes its own set of terminiology:

- flex-container: the container or parent of the items wanting to be manipulated

  ![img](https://css-tricks.com/wp-content/uploads/2018/10/01-container.svg)

- flex-items: the children of the container that reside inside it.

  ![img](https://css-tricks.com/wp-content/uploads/2018/10/02-items.svg)

- regular layouts are based on `block` and `inline` flow directions. flexbox is based on `flex-flow` directions.

### Example 1

```html
  <div class="container">
    <form action="">
      <div class="form-row">
        <label for="name">Name:</label>
        <input type: "text" id="name" />
      </div>
      <div class="form-row">
        <label for="favColor">Favorite Color:</label>
        <input type: "text" id="favColor" />
      </div>
    </form>
```

```css
body {
  font-family: Arial, Helvetica, sans-serif;
}

.form-row {
  padding: 10px 0;
  display: flex;
}

.form-row label {
  padding-right: 10px;
}

.form-row input {
  flex: 1;
}
```

to **stretch the inputs** to the width of the container:

- give the parent elements the `display:flex` option. By default
- give the child `input` a `flex` of `1`
- we don't want the `label` to flex otherwise it would take up half the page so leave it blank

![image-20210415055741398](C:\Users\Karis\AppData\Roaming\Typora\typora-user-images\image-20210415055741398.png)

the input stretches all the way to the edge of the screen

### Example 2

```html
<div class="column-layout">
    <div class="main-column">
      <h1>Main Column</h1>
      <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Donec et mollis odio, sagittis iaculis odio. Nulla varius id nunc vitae condimentum. Sed quis maximus libero. Quisque ut augue facilisis ante dictum ornare a a metus. Curabitur fringilla elit at lectus volutpat auctor. Nunc condimentum accumsan sapien ac feugiat. Nam sed consequat leo. Nulla varius faucibus nunc, sed rhoncus urna venenatis quis. Mauris hendrerit molestie congue. Suspendisse ut dolor quis enim mattis vulputate ut non arcu.</p>
    </div>
    <div class="sidebar1">
      <h2>Sidebar 1</h2>
      <p>Integer consequat lorem eu quam pharetra, fringilla tempus mi placerat. Nullam ullamcorper rhoncus dui sit amet gravida. Integer at egestas turpis.</p>
    </div>
    <div class="sidebar2">
      <h2>Sidebar 2</h2>
      <p>Morbi turpis turpis, luctus sit amet lacus ornare, aliquam placerat tortor. Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia curae; Donec non posuere risus.</p>
    </div>
```

```css
.column-layout {
  max-width: 1300px;
  background-color: #FFF;
  margin: 40px auto 0 auto;
  line-height: 1.65;
  padding: 20px 50px;
  display: flex;
  font-family: Arial, Helvetica, sans-serif;
}

.main-column {
  flex: 2;
  order: 2;
}

.sidebar1 {
  flex: 1;
  order: 1;
}

.sidebar2 {
  flex: 1;
  order: 3;
}
```

![image-20210415062855116](C:\Users\Karis\AppData\Roaming\Typora\typora-user-images\image-20210415062855116.png)

to create a **3 column layout**:

- add the `display:` flex property to the parent
- using property`flex` on the children indicates which child is the largest of the 3

- `main-column` is given a `flex` of `2` as we want it to be double the size of the other 2 columns which are given `flex: 1` (by default flex is set to 1)
- to reorder the columns without touching the html, use `order` property and set each to the order you want it to flow on the page (by default order is set to how it appears on html)

### Example 3

```html
div class="call-outs-container">
    <div class="call-out">
      <h4>Feature 1</h4>
    <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed auctor nisi vel diam bibendum porttitor. Curabitur sed suscipit libero. Pellentesque vulputate nisl vitae erat posuere, sagittis pulvinar turpis eleifend.</p>
    </div>
    <div class="call-out">
      <h4>Feature 2</h4>
    <p>Etiam laoreet porta volutpat. Aliquam ullamcorper sem vitae interdum viverra. Integer id augue tempus enim pretium vulputate at at eros. Ut dapibus ex vel congue mollis.</p>
    </div>
  <div class="call-out">
      <h4>Feature 3</h4>
    <p>Nunc lobortis quis sapien sed venenatis. Praesent vel sodales nulla. Pellentesque felis erat, faucibus vel efficitur nec, blandit et nulla.</p>
  </div>
```

```css
.call-outs-container {
  display: flex;
  max-width: 1400px;
  justify-content: space-between;
}

.call-out {
  box-sizing: border-box;
  padding: 0 20px;
  flex-basis: 32%;
}
```

![image-20210415092231081](C:\Users\Karis\AppData\Roaming\Typora\typora-user-images\image-20210415092231081.png)

adding **margins** between elements in flexbox can be done with:

- adding a `width` or `flex-basis` of `~30%` (3 columns)
- adding the property `justify-content` with a value of `space-between` . By default `justify-content` is set to `flex-start`
- `align-items` plays with the vertical property. By default the value is set to `stretch` which will stretch to the width of the container.

#### For media Queries:

- cut the flex properties from the mobile friendly site and let it kick in only when the user works with screen sizes that are 900px or wider:

```css
.call-outs-container {
  max-width: 1400px;
}

.call-out {
  box-sizing: border-box;
  padding: 20px;
  margin-bottom: 20px;
  flex-basis: 32%;
}

@media (min-width: 900px) {
  .call-outs-container {
    display: flex;
  	justify-content: space-between;
  }
}
```

![image-20210415094611161](C:\Users\Karis\AppData\Roaming\Typora\typora-user-images\image-20210415094611161.png)

### Example 4

This is particularly useful with multiple rows of items that each have a fixed width: 

![image-20210415095241803](C:\Users\Karis\AppData\Roaming\Typora\typora-user-images\image-20210415095241803.png)

add to the parent container:

- the property of `flex-wrap: wrap` (by default this has a value of `no-wrap`) to drop down to multiple rows as width of the screen decreases.

![image-20210415095327396](C:\Users\Karis\AppData\Roaming\Typora\typora-user-images\image-20210415095327396.png)

### Example 5

When dealing with **simple centering** vertically and horizontally inside a container:

- to the parent container add `display: flex`
- to the child add `margin` of `auto`

### example 6

from this:

![image-20210415100101791](C:\Users\Karis\AppData\Roaming\Typora\typora-user-images\image-20210415100101791.png)

to this: a two column layout with one main column and 2nd **column divided vertically:**

![image-20210415095945773](C:\Users\Karis\AppData\Roaming\Typora\typora-user-images\image-20210415095945773.png)

```html
<div class="equal-height-container">
  <div class="first">
    <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed auctor nisi vel diam bibendum porttitor. Curabitur sed suscipit libero. Pellentesque vulputate nisl vitae erat posuere, sagittis pulvinar turpis eleifend.</p>
  </div>
  <div class="second">
    <div class="second-a">A</div>
    <div class="second-B">B</div>
  </div>
</div>
```

```css
.equal-height-container {
  max-width: 900px;
  margin: 0 auto;
  display: flex;
}

.first {
  background-color: #FFF;
  padding: 20px;
  flex: 1;
}

.second {
  background-color: yellow;
  flex: 1;
  display: flex;
  flex-direction: column;
}

.second-a {
  background-color: #c0dbe2;
  flex: 1;
}

.second-b {
  background-color: #cdf1c3;
  flex: 1;
}
```

To achieve this look and **nest flexboxes**:

- `second` is a parent to 2 children `second-a` and `second-b` 
  - `second` needs to be given the `display: flex` property
  - with a `flex-direction` of `column` . By default it is set to `row`
- each child of `second` must be given a `flex` of `1` to fill up the space evenly of the container

- As before the primary parent `equal-height-container` must be given a display of `flex`
  - its children must be given a `flex` of `1`