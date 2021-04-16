## What are CSS Frameworks?

The most common css frameworks around are Twitters bootstrap and Foundation. The main advantage these frameworks have are the way they handle media queries for tablets and mobiles and a predefined grid system created with generic classes. 

While flex or grid may override the usefulness of css frameworks, not all browsers support flex or grid being relatively new technology. css frameworks should also enhance overtime to keep up with flex and grid.

CSS frameworks while useful have a short / dynamic lifespan and aren't considered to be a fundamental skill because of this. With a strong fundementals in CSS any framework can be learned with ease.

Framework packages are comprised of a grid system created with HTML CSS and Javascript. This isn't related to CSS grid

Column containers use relative widths (percentages, rems) so nesting can be achieved.

If we want to create a horizontal list of 4 columns evenly divided it might look like so:

```css
ul {
  padding: 0;
}
/* to get rid of whitespace we float left...*/
.one-fourth {
  display: inline-block;
  float: left;
  outline: 1px solid gray;
  vertical-align: top;
  width: 25%;
}
/*...and clear */
.row::after {
  clear: both;
  content: "";
  display: block;
  line-height: 0;
}
```

```css
<ul class="row">
  <li class="one-fourth">8 GB SD card</li>
  <li class="one-fourth">16 GB SD card</li>
  <li class="one-fourth">32 GB SD card</li>
  <li class="one-fourth">64 GB SD card</li>
</ul>
```

![Simple 4-Column Layout](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_6/frameworks-01.png)

We can use the same approach for 2, 3, or 6 columns:

![Mixed Layout](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_6/frameworks-02.png)

because we have worked with relative widths, nesting columns work well. And this is the basis on CSS frameworks: A grid system is created using classes, where your HTML uses the classes to structure the webpage. They also provide responsive design too.