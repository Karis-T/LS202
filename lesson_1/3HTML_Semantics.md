## HTML Semantics

**Semantic HTML**: uses HTML to indicate the structure and purposes of the document, rather than its presentation.

In HTML5 all tags are semantic except for <div> and <span>. HTML4 prescribes that <b> and <i> are non-semantic but that is now changed in 5. They have subtle differences between <strong> and <em> so make sure you know what they are.

Understanding semantics takes time. Just try not to use non-semantic tags and avoid misusing the semantic ones and you should be okay.

### Semantic HTML Table

| element                 | purpose                                                      | example                                                      |
| ----------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| <nav>                   | major navigation block                                       | navigation links                                             |
| <article>               | self contained and reusable. independent content that makes sense on its own | blogs, comments, news article, widget, forum post            |
| <aside>                 | content that's tangentially related to the page. Not always required to understand the current content. | Sidebar, comments section, pull quotes, glossary, ads, footnotes. |
| <blockquote>            | extended section quoted from another source                  | famous quotes, direct textbook or journal facts and figures  |
| <figure> & <figcaption> | An aid to understanding the content and Can be referred to by an appendix | One or more images, graphics, code samples                   |
| <section>               | Apart of a larger body of work or maind document flow and isn't standalone like an <aritcle>. Required to understand the content and uses a heading | section of a page, chapter of an <article>, needs a heading  |
| <main>                  | Shows screen readers where the main content begins. Should be used only once per page. | previews to articles, services, portfolios. The main content of your webpage. |
| <header>                | introduction content, the <header> sits at the top of a <section> or <article> | headings, table of contents, logos, search forms and navigation |
| <footer>                | sits at the bottom of a <section> or <article> that contains additional information about the section | author, links to related documents, copyright data contact details etc. |
| <address>               | contact information for the section it sits inside           | phone number, address, socials, email                        |

| element      | purpose                                                      | example                                        |
| ------------ | ------------------------------------------------------------ | ---------------------------------------------- |
| <i>          | alternative voice text                                       | "I said 'Hello.' She said *'Goodbye.'*"        |
| <b>          | Stylistically offset text, such as keywords                  | "ES6 adds the keywords **const** and **let**." |
| <em>         | Adds *emphasis* to the text; most browsers use italics       | "We do them because they are *hard*!"          |
| <strong>     | The text has **greater importance** than the surrounding text; most browsers use boldface | "You **must** remember to turn the light off!" |
| <p>          | provides the ability to define paragraphs                    | paragraphs                                     |
| <a>          | provides the ability to define both internal and external code anchors or hyperlinks | arbitrary links                                |
| <h1> to <h6> | Provides headings to create visual hierarchy and to be processed by screen readers and search engines for better indexing | headings                                       |

<p style="border: 1px solid grey; padding: 3% 4% 4% 4%;">
Don't use headings when you only want to change font sizes. Headings h1 to h6 have a semantic meaning and if used as font sizes it makes it harder for search engines and assistive tech to understand your web page. Misusing HTML for stylistic reasons makes it hard for other developers to understand your code as well.
</p>



### Non-Semantic HTML Table

| element | purpose                                                      | example                                     |
| ------- | ------------------------------------------------------------ | ------------------------------------------- |
| <div>   | no special meaning and as a block level element it's used to represent its children. You can give it semantics with attributes like class or id, but it alone is anonymous. | groups larger content for styling purposes  |
| <span>  | has no semantic meaning but  as an inline level element that can be used with attributes like class or dir to give it meaning. It represents its child | groups smaller content for styling purposes |

### Examples

```html
<!--- wrapping an article around a blockquote --->
<article>
  <blockquote>
    <h1>Lincoln's Gettysburg Address</h1>
    <p>Four score and seven years ago ...</p>
    <p>Now we are engaged in a great civil war...</p>
    <p>But, in a larger sense, we can not dedicate...</p>
  </blockquote>
</article>
```

```html
<!--- aside tag example --->
<h3>Hex Colors</h3>

<p>
  Most graphics and design applications like Photoshop and Pixelmator
  display colors in hexadecimal format, so it's easy to copy and paste
  color values you need from one program into your editor as a CSS
  property.
</p>

<aside>
  <p>
    If you're unfamiliar with the hexadecimal numbering system, it uses 16
    different digits instead of the ten the decimal system uses. The hex
    digits are 0 through 9, as in the decimal system, but also include a
    through f (or A through F) as valid digits.
  </p>
</aside>
```

```html
<!--- section tag example --->
<section>
  <h3>Text-align Property</h3>
  <p>
    Given the width of the paragraph, the heading looks odd hanging out 		on the left side of the screen. Let's center it instead; we'll do 			this with the text-align property:
  <p>
</section>
```