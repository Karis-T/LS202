### What are Liquid Layouts?

Liquid layouts use percentage widths to maintain same ratios for content as the browser alters screen sizes. They normally take up the entire width of the browser. 

```html
<main>
  <article class="content">
    Enim Lorem aliqua anim nulla labore nulla ullamco. Deserunt fugiat duis ex dolor. Ex laboris ad officia minim quis.  Incididunt eu reprehenderit ullamco eiusmod dolor pariatur mollit qui. Officia aliqua velit deserunt adipisicing duis minim minim tempor.
  </article>
  
  <aside class="sidebar">
		Proident cillum ad cillum minim magna. Duis nulla est est non sunt. Est culpa laborum velit dolor.
  </aside>
</main>
```

```css
html {
  font-size: 16px;
}
body, article, p {
  margin: 0;
  padding: 0;
}
body {
  margin: 0;
  padding: 0.5rem;
}
main {
  clear: both;
  overflow: hidden;
  padding-bottom: 1.5rem;
}
.content,
.sidebar {
  box-sizing: border-box;
  float: left;
  padding: 20px 30px;
}
.content {
  background-color: pink;
  width: 70%;
}
.sidebar {
  background-color: cyan;
  width: 30%;
}
```

![image-20210416134948462](C:\Users\Karis\AppData\Roaming\Typora\typora-user-images\image-20210416134948462.png)

No matter the browsers width the two columns maintain their width ratio. As the browser width changes, so does the content width.

### What are Fluid Layouts?

If you want to restrict the expansion of the layout, use a fluid layout instead of Liquid. Once the window reaches a limit it will cease expanding/collapsing and remain fixed. 

```css
main {
  max-width: 1000px;
  min-width: 500px;
}

.content,
.sidebar {
  padding: 20px 30px;
}

.content {
  box-sizing: border-box;
  float: left;
  width: 70%;
}

.sidebar {
  overflow: hidden;
}
```

When the browser window is resizes the layout will change until it reaches its `min-width` or `max-width`