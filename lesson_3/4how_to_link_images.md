## How to Use Images as Links

**any non-interactive element can be used as a link - including images**. (this excludes form controls and other links)

to make an image linkable to another page place the `img` tag inside an `a` tag: 

```html
<a href="https://someurldestination.com">
  <img src="https://image_location.jpg" alt="image description" />
</a>
```

if the image URL (src) is the same as destination URL (href), then it allows you to view the image resource by itself in its original size or fit to screen toggle feature.