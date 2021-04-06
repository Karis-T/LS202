## Building Lists in HTML & CSS

### Nested Lists

html: 1 giant description list with 3 groupings:

- first grouping has 1 term and 3 definitions
  - within the last definition is an unordered list with 3 bullet points
- second grouping has 1 term and 2 definitions
  - within the last definition is an ordered list with 3 numbers
- third grouping has 2 terms and 2 definitions
  - within the last definition has a description list with 3 groupings 

```html
<dl>
  <dt>Unordered</dt>
  <dd>A simple list with bullets.</dd>
  <dd>A plain list with no bullets or sequence numbers.</dd>
  <dd>
    <ul>
      <li>Red</li>
      <li>Green</li>
      <li>Blue</li>
    </ul>
  </dd>

  <dt>Ordered</dt>
  <dd>A simple list with a visible sequence.</dd>
  <dd>
    <ol>
      <li>Red</li>
      <li>Green</li>
      <li>Blue</li>
    </ol>
  </dd>

  <dt>Description</dt>
  <dt>Definition</dt>
  <dd>A list with terms and definitions.</dd>
  <dd>
    <dl>
      <dt>Red</dt>   <dd><div class="red"></div></dd>
      <dt>Green</dt> <dd><div class="green"></div></dd>
      <dt>Blue</dt>  <dd><div class="blue"></div></dd>
    </dl>
  </dd>
</dl>
```

css:

```css
li, dd, dt {
  font-size: 1.25rem;
}

.red, .green, .blue {
  width: 50px;
  height: 25px;
}

.red {
  background-color: red;
}

.green {
  background-color: green;
}

.blue {
  background-color: blue;
}
```

Example:

![Nested lists](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_4/lists-overview-04.png)



the next example exclusively uses unordered lists to demonstrate that the bullets change when you nest unordered lists. Ordered lists and description lists do not share this trait 

- the entity `&39608` is a solid rectangle character for a full block. █

```html
<ul>
  <li class="red">
    Red
    <ul>
      <li>&#9608;&#9608;&#9608;</li>
      <li>#ff0000</li>
      <li>rgb(255, 0, 0)</li>
    </ul>
  </li>

  <li class="green">
    Green
    <ul>
      <li>&#9608;&#9608;&#9608;</li>
      <li>#00ff00</li>
      <li>rgb(0, 255, 0)</li>
    </ul>
  </li>

  <li class="blue">
    Blue
    <ul>
      <li>&#9608;&#9608;&#9608;</li>
      <li>#0000ff</li>
      <li>rgb(0, 0, 255)</li>
    </ul>
  </li>
</ul>
```

```css
.red {
  color: red;
}

.green {
  color: green;
}

.blue {
  color: blue;
}
```

![Nested lists](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_4/lists-overview-05.png)

### Navigation Menus

Typically developers use **unordered lists** to build website navigation menus. They are either constructed vertically or horizontally. 

- for vertical lists perform the following:
  - remove bullets with `list-style` or `list-style-type` property
  - bring the `padding-left` back to `0`
  - set the navigation anchors `text-decoration` to `none` to remove underline link
  - to increase top bottom padding adjust `line-height`
  - to increase left-right padding adjust `padding` 
- for horizontal lists perform the following:
  - set `width` of the `ul` to 100%
  - set `li` to `inline-block`
  - set `li` to a percentage width (possibly 25%)
  - `text-align` `li` to `center`

#### vertical navigation bar

```html
<nav>
  <ul>
    <li><a href="#">Home</a></li>
    <li><a href="#">Projects</a></li>
    <li><a href="#">Team</a></li>
    <li><a href="#">Help</a></li>
  </ul>
</nav>
```

```css
nav ul {
 background-color: powderblue;
 list-style-type: none;
 padding-left: 0;
 width: 200px;
}

nav li {
 color: blue;
 font-size: 1.25rem;
}

nav a {
 box-sizing: border-box;
 color: blue;
 display: inline-block;
 line-height: 2.5;
 padding: 0 10px;
 text-decoration: none;
 width: 100%;
}

nav a:hover,
nav a:focus {
 background-color: blue;
 color: white;
}
```

![image-20210404130345234](C:\Users\Karis\AppData\Roaming\Typora\typora-user-images\image-20210404130345234.png)

#### horizontal navigation bar

Remove whitespace by removing all spacing in the html:

```html
<nav>
  <ul>
    <li><a href="#">Home</a></li><li><a href="#">Projects</a></li><li><a href="#">Team</a></li><li><a href="#">Help</a></li>
  </ul>
</nav>
```

```css
nav ul {
  font-size: 0;
  width: 100%;
  list-style: none;
  padding-left: 0;
}

nav li {
  display: inline-block;
  font-size: 1.25rem;
  text-align: center;
  width: 25%;
}

nav a {
 box-sizing: border-box;
 color: blue;
 display: inline-block;
 line-height: 2.5;
 padding: 0 10px;
 text-decoration: none;
 width: 100%;
}

nav a:hover, nav a:focus {
 background-color: blue;
 color: white;
}
```

you can remove whitespace in the html using the `font-size` property.  set the `nav ul` to `0` then reinstate the `font-size` in the `nav li` selector.

![image-20210404130311471](C:\Users\Karis\AppData\Roaming\Typora\typora-user-images\image-20210404130311471.png)