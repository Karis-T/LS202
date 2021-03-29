## How to Add Images to Web Pages

```html
<img src="lucrezia.jpg" alt="Da Vinci's Smarter Sister, Lucrezia"
     width="800" height="600" />
```

A typical `<img>` tag

### How do I use the `<img/>` element?

`<img>` tag's load and display a **foreground** image from a resource. 
It has 4 useful attributes: 

- `src` source: **required** attribute that tells the browser where to find an image. 
  - Uses the same URL format as anchor tags and is either relative, root-relative or absolute.
- `alt` alternative: **optional** attribute that describes the content of the image. 
  - It's used as an assistive aid for screen readers, search engines and people with poor vision. 
  - It's also used when browsers are unable to display the image. 
  - images with no alt tag may be skipped by screen readers and considered 'non essential'. 
  - alt tags improve websites SEO
  - although not required, standard say you should use it in most cases. HTML won't be considered valid on W3c unless you use `alt` tags
  - If your image isn't considered important enough, specify it with `alt=""` 
- `width` & `height`: **optional** attributes that specify image width and height in px
  - CAUTION: CSS `width` and `height` properties *override* these attributes
  - use if you always want to display images with a specific width and height
  - browser optimizes rendering speed by allocating room before download
  - if you don't know specific width and height in advance use CSS instead

### What is `<figure>` and `<figcaption>`?

```html
<figure>
  <img src="masthead.jpg" alt="Sunset over the forest" />
  <figcaption>The sun sets over the dense forest</figcaption>
</figure>
```

A typical `<figure>` and `<figcaption>` tag

If you want to indicate a relationship between an image and its caption, `<img>` and `<p>` tags won't help. Instead use `<figure>` with optional `<figcaption>` which creates a semantic meaning between image and content.

figures are used for the purposes of illustrating the surrounding content and usually consists of an image, video or audio.

Don't use `figure` and `figcaption` if you're not referencing it in the text. If your image doesn't need a caption, don't use `figcaption`. Things like logos, icons, BG images etc are for decorative purposes only and are not considered `figure`s.