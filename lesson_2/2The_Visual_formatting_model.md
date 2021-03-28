## What is the Visual Formatting Model?

The browser uses the CSS box model to lay out HTML elements and text. As mentioned before by default these elements have a `display` property of `inline-block`, but there are a dozen more ways to layout the page. 

The most common ones are `block`, `inline` and `inline-block`. The `display` property and all its values are known as the **visual formatting model.** 

### What are Block Elements?

>A block-level element always starts on a new line and takes up the full width available (stretches out to the left and right as far as it can).

`block` elements group one or more elements into an area on the page. These elements are called **containers** and the master container is the `body` to which all other elements belong.

`block` elements sitting inside the `body` stack on top of each other- like a stack of blocks. This make it easy and predictable to use them. Even though `block` elements take up an entire row it doesn't actually alter the `width` of the element.

`block` elements are made up of width, height, margin, border and padding. The browser will calculate all of this and draw the box with its final dimensions. 

<div style= "border: 1px solid grey; padding: 2% 4%">
  <p>
    Note 1: Another way to talk about containers is to refer to them as parents and the elements nested within them as children. 
  </p>
  <p>Note 2: The width and height of an element may incorporate the padding and border if you have box-sizing active.</p> 
  <p>Note 3: the height and width never incorporate the margins as margins are designed to put spacing between elements but it does need to be considered when determining if an element will fit in a space or not.</p>
</div> 

A common list of `block` elements see [mdn](https://developer.mozilla.org/en-US/docs/Web/HTML/Block-level_elements#Elements) for the complete list:

- `section`, `article`, `aside`, `header`, `footer`
- `p`
- `h1` through `h6`
- `blockquote`
- `ul`, `ol`, `dl`
- `figure` and `figcaption`
- `form` and `fieldset`

While HTML standards don't define elements as `block` or `inline` in practice every `block` has a visual display mode. You can convert any inline element using the `display: block` property (`a` and `img` can be rendered as `block`)

### What are inline elements?

>An inline element does not start on a new line and only takes up as much width as necessary.

Browsers use inline elements to alter to the way small sections of text are displayed. This allows the reader to find specific items in a sea of other elements. eg boldface text inside a paragraph.

Inline elements handle the properties width height padding border margin differently from block elements. 

A common list of `inline` elements. See [mdn](https://developer.mozilla.org/en-US/docs/Web/HTML/Inline_elements#Elements) for the complete list:

- `span`
- `b`, `i`, `u`, `strong`, `em`
- `a`
- `sub` and `sup`
- `img`

Below may either default to `inline` or `inline-block` depending on the browser:

- `button`
- `select`
- `textarea`
- `input`

Unlike `block` elements, `inline` elements aren't as straightforward. Here are some of their rules. 

<strong style="color: lime">`Inline` elements use:</strong>

- *left* & *right* margins & padding the same way as `block` elements do
- borders (but it may look weird)
- top and bottom **padding** (this isn't seen unless you have a border/background)
- `width` and `height` are computed from element content

<strong style="color: red">`Inline` elements ignore:</strong>

- `width` and `height` properties (images are the exception)
- top and bottom **margins**

You can override a previous declaration element and convert it to `display: inline`

#### How do Borders, Padding, Margins work with Inline Elements?

See this as something you need to avoid rather than make use of.

```css
em {
  background-color: rgba(255, 255, 0, .5);
  border: 30px solid rgba(255, 0, 64, .5);
  margin: 40px;
  padding: 30px;
}
```

![Inline borders, padding, and margins](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_2/the-visual-formatting-model-01.png)

*left and right* factors **affect the surrounding flow of elements** whereas the *top and bottom* do not. 

### What are inline-block elements?

`inline-block` is a legacy model and is replaced by `inline flow-root`. However many websites still use the original and it will be awhile before the new one gains popularity.

`inline-block` is a mixture of the two types: It acts like a `block` element but instead of taking up a whole row, elements now sit side by side with other `inline / inline-block` elements. They will only drop to the next line when the elements `width` greater than the containers `width`.

`inline-block` differs from `inline` in that they can use `width` and `height` properties. `padding` `borders` and `margin` all work like `block` elements.

Browsers enable vertical alignment **for neighboring `inline-block` and `inline` elements.** (this only works if you have a bigger adjacent element)

There are some inconsistencies with browsers defining default display styles- eg. chrome and safari define `input` and `textarea` elements as `inline-block` whereas Firefox defines them as `inline`. If this is a problem, explicitly set the display property to the preferred value:

```css
input, textarea {
  display: inline-block;
}
```

### How does Nesting elements and the Visual Display Model Work?

You cannot nest `block` and `inline-block` elements inside `inline` elements. The `a` tag is the exception to this rule provided it doesn't contain any interactive elements like `input`, `button`, `select`, `textarea` or even annother `a` tag.

Even though your browser may render invalid / improper nested elements correctly, other browsers may not. if W3c complains its a good idea to correct it.

```html
<!--- improper use of inline elements even though it may render --->
<strong><em>This is strong emphasized text</em></strong>
<!--- never ignore mis nesting like below --->
<strong><em>This is strong emphasized text</strong></em>
```

### What are some other Visual Display Models?

2 dozen visual display models are available but don't bother memorizing them until you need them. Among them are the display models `flex` and `grid` which solve a lot of design problems for front-end developers.