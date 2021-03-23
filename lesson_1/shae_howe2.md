## Get to Know HTML

### What are semantics and why is it important?

Semantics are giving content structure and meaning to each element by describing the *value* of the content, regardless of styling. This allows search engines and screen readers to be able to easily identify what's on a page. It also renders the page more readable to developers.  

### What are `<div>` and `<span>` and what are block and inline level elements?

<div style="border: 1px solid grey; padding:4% 4% 2% 5%;"><strong>Block vs Inline level Elements:</strong> Most elements are either one or the other 
	<ul>
		<li><strong>Block level elements:</strong> begin on a new line and occupy any available width and stack on top of each other. You can nest block level elements and have the ability to wrap inline level elements. We typically use block level elements for large pieces of content like paragraphs.</li>
  	<li><strong>Inline level elements:</strong> do not begin on a new line and take up as much space as the width of their content. They line up one after another and sit in the normal flow of the document. They are able to be nested, but you cannot wrap block level elements. They're typically for smaller pieces of content such as a few words.</li>
  </ul>
</div>

`<div>` and `<span>` are containers for styling purposes and don't hold any semantic value. They are however great for creating targeted styles for specific content.

- `<div>` : block level element used for large grouped styling
- `<span>` : inline level element used for small grouped styling within a block-level element

`<div>` and `<span>` are assigned `class` or `id` attributes for styling purposes. Choose names that reflect the content not the style/appearance incase it were edited later on.

```html
<div class="social">
  <p>Find me on facebook</p>
  <p>Find me also on Instagram</p>
</div>

<p>Soon we'll be <span class="tooltip">writing HTML</span></p>
```

<div style="border: 1px solid grey; padding:4% 4% 2% 5%;"><strong>Commenting with html and css</strong> help keep files organized and are useful for multiple people working on the same files
  <ul>
    <li>HTML: < !--- comment goes here --- ></li>
    <li>CSS: /* comment goes here */</li>  
  </ul>
</div>

### What text-based elements best represent page content?

Text is the most predominant form of media on the web. The most popular HTML text-based elements are paragraphs, headings, strong and emphasis. 

###### Headings

Headings help break up content and create visual hierarchy for readers. Headings also provide more accurate indexing for search engines. Headings should be used semantically and not for the purposes of emphasizing - there are better ways to handle that. Headings are blocks level elements and start at `h1` for the biggest and `h6` for the smallest heading.

```html
<h1>Heading Level 1</h1>
<h2>Heading Level 2</h2>
<h3>Heading Level 3</h3>
<h4>Heading Level 4</h4>
<h5>Heading Level 5</h5>
<h6>Heading Level 6</h6>
```

###### Paragraphs

Typically paragraphs follow a heading and are reserved for chunks of text. They are also block level elements that use the `p` tag.

``` html
<p>Steve Jobs was a co-founder and longtime chief executive officer at Apple. On June 12, 2005, Steve gave the commencement address at Stanford University.</p>

<p>In his address Steve urged graduates to follow their dreams and, despite any setbacks, to never give up–advice which he sincerely took to heart.</p>
```

###### Bold text using `<strong>`

`<strong>` is an inline element that highlights content of strong importance. This differs from `<b>` in that bold is used to stylistically offset text. Out of the two `<strong>` is favored as it semantically describes content of great importance.

```html
<p><strong>Caution:</strong> Falling rocks.</p>
<p>This recipe calls for <b>bacon</b> and <b>baconnaise</b>.</p>
```

###### Italicize text using `<em>`

`<em>` is also an inline element and much like `<strong>` has two versions that have different intentions. `<em>` is designed to stress emphasis on content, whereas `<i>` is intended to italicize and give text an alternative voice or tone.

```html
<p>I <em>love</em> Chicago!</p>
<p>The name <i>Shay</i> means a gift.</p>
```

### What are the HTML5 structural elements and how do we defined the structure and organization of our page content?

the structure of a webpage used to be built using divisors but lacked descriptive value and was rather confusing to understand their intention. Fortunately HTML5 introduced semantic elements which are all block level and can be used multiple times throughout a page. Their goal is to improve organization and provide structural semantics.

###### `<header>`

identifies top of an article, segment, section or page. It's typically a heading, intro text or even navigation

<div style="border: 1px solid gray; padding: 1% 4% 2% 4%">
  <h6> < header > vs < head > vs < h1-h6 > elements</h6>
  <ul>
 		<li>< header >falls within the body element and outlines heading of a segment of a page</li>
		<li> < head > isn't displayed on the page and contains meta data about the page. Sits above the body element in the html element</li>
		<li>< h1 to h6 > indicate text headings and provide textual heirarchy to a page.</li>
  </ul>
</div>

###### `<nav>`

reserved for links to related pages or different sections of the same page. Nav element is used for primary navigation only, such as contents, previous / next links or global navigation etc. They shouldn't be for misc one-off links - that's the anchors job. 

###### `<article>`

The content contained within an article should be independent of the html page it currently resides within. It should remain independent and is suited for distribution purposes. eg blog posts, newspaper articles, user posted content etc.

###### `<section>`

Commonly used to break up and provide hierarchy to a page, sections group related, thematic content. They often include a heading. 

<div style="border: 1px solid gray; padding: 1% 4% 2% 5%">
  <h6> < article > vs < section > vs < div > elements</h6>
  <p>refer to the content itself when deciding which to choose between the 3</p>
  <ul>
 		<li>if the content is grouped for the purposes of styling use div</li>
		<li>if the content can be independently distributed use article</li>
		<li>if the content contributes to outlining the document use section</li>
  </ul>
</div>

###### `<aside>`

As a block element aside occupies the full width of the page or the parent its nested within. It describes content related to its surroundings such as sidebars, inserts or brief Explanations - eg. for an article an aside element could be content about the articles author.

###### `<footer>`

Found at the end of a section, article or page, it describes information relative to the section or document its located in. It's typically placed at the bottom of its parent.

<div style="border: 1px solid gray; padding: 1% 4% 2% 5%;">
  <h6>encoding special characters</h6>
  <p>like urls, special characters like accents, punctuation and symols like the copyright symbol must be encoded. In HTML they can be misunderstood or be misused. To encode a special character they must be prefixed with '&' followed by its <a href="http://copypastecharacter.com/">chracter encoding</a> and then suffixed with a semicolon ';'</p>
</div>



![](https://learn.shayhowe.com/assets/images/courses/html-css/getting-to-know-html/building-structure.png)

### How do we use hyperlinks to navigate between web pages and websites?

Hyperlinks create a link from one resource on the internet to another. In HTML they are implemented using the inline anchor element `<a>` in conjunction with the `href` or hyperlink reference attribute where its value is the location or URL of the resource.

```html
<a href="http://shayhowe.com">Shay Howe</a>
```

<div style="border: 1px solid grey; padding:1% 4% 2% 5%;">
   <h6>Wrap block level elements with anchors</h6>
   <p>HTML5 enables inline elements to wrap block elements. This allows large blocks of content to be wrapped by anchors, turning it into a link.</p>
</div>

###### Relative and absolute paths

- **Relative Paths** are for pages within the same website. This means you will only need to type the file path of where the page is located relative to the current page's directory.
- **Absolute paths** are for pages located on a different website. This means you will need to type the absolute full address / url to locate that resource on the internet. 

```html
<a href="about.html">About</a>
<a href="https://google.com/">Google</a>
```

###### Links to email addresses

Just like http we can also make email requests using the `mailto:` scheme followed by desired email. Just like http get requests, we can also supply query strings with `subject` and `body` parameters. The same rules apply with the query beginning with `?` key value pairs separated by `=` and multiple parameters separated by `&`. ASCII Encoding applies here too with `%20` for spaces and `%0A` for line breaks

```html
<a href="mailto:shay@awsome.com?subject=Reaching%20Out&body=How%20are%20%you">Email Me</a>
```

###### Open links in a new window

You can open a new window using the `target` attribute which indicates where the link will be displayed. It's value should be `"_blank"` which indicates a blank window

```html
<a href="https://shayhowe.com" target="_blank">Shay Howe</a>
```

###### Link to parts of the Same page

We can link to parts on the same page using the `id` attribute followed by a unique value. We can then reference this value prefixed with a hash within a `href`'s value. An example of this is the "back to top" button or link.

```html
<body id="top">
  ...
  <a href="#top">Back to top</a>
  ...
</body>
```