## How to Apply Images as a Background

**You can set the background of a HTML page as an image using CSS.** This is done with the `background` or `background-image` property. 

Images appear as a background for the selected element (and its nested elements if its a container)

If its a BG image for the entire page we use the `body` selector to set the image.

```html
<section>
  Sint duis dolor consectetur ad nostrud sint. Occaecat reprehenderit officia ex
  duis velit veniam magna labore.
</section>

<nav>
  <ul>
    <li><a href="#">Home</a></li>
    <li><a href="#">Work</a></li>
    <li><a href="#">Play</a></li>
  </ul>
</nav>
```

```css
body {
  font-size: 32px;
  background-image: url("http://d3jtzah944tvom.cloudfront.net/202/images/lesson_3/gradient-background.png");
}

section {
  display: inline-block;
  width: 500px;
}

nav {
  background-image: url("http://d3jtzah944tvom.cloudfront.net/202/images/lesson_3/blurry.png");
  display: inline-block;
  height: 200px;
  width: 250px;
}
```

![Background image](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_3/adding-images-to-web-pages-01.png)

Other properties associated with image background include image size, positioning, and repeat counts.

```css
body {
  background-size: 25%;
}
```

![Sized background image](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_3/adding-images-to-web-pages-02.png)