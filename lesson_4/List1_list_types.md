## List Types

HTML gives you just **6 tags** to build 3 different kinds of lists: **unordered,** **ordered** and **description**

### Unordered Lists

- 'unordered' lists often have an implied order 
- They have no explicit number or naming system
- instead they have *bullets* in the form of dots, discs, circles or squares
- by default browsers render unordered lists *vertically*
- You can customize by displaying items horizontally
- you can also hide bullets or create custom bullets.

To build unordered lists in HTML use `<ul>` and `<li>` tags:

```html
<ul>
  <li>Red</li>
  <li>Orange</li>
  <li>Yellow</li>
  <li>Green</li>
  <li>Blue</li>
  <li>Indigo</li>
  <li>Violet</li>
</ul>
```

![An unordered list](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_4/lists-overview-01.png)

### Ordered Lists

- 'ordered' lists have an explicit order visually displayed as a sequence
- by default browsers render ordered lists vertically as consecutive numbers
- can be customized to display roman numerals or the alphabet- English or foreign.
- use the boolean attribute `reversed` to reverse the order of the list. pre HTML5 it would be written `reversed="reversed"`
- Examples of an ordered lists could be "The Top 10 Programming Languages" or a sequence of "steps to make a pot of coffee"

 To build unordered lists in HTML use `<ol>` and `<li>` tags:

```html
<ol>
  <li>Red</li>
  <li>Orange</li>
  <li>Yellow</li>
  <li>Green</li>
  <li>Blue</li>
  <li>Indigo</li>
  <li>Violet</li>
</ol>
```

![An ordered list](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_4/lists-overview-02.png)

### Description Lists

- 'description lists' are a list of terms and definitions
- each grouping may have 1 or more term `<dt>` and 1 or more definition `<dd>`
- pre HTML5 they were called *'definition lists'*
- Example of a description list could be a dictionary, bibliography or phone books

To build a description in HTML list use `<dl>`, `<dt>` and `<dd>` tags:

```html
<dl>
  <dt>Unordered</dt>
  <dd>A simple list with bullets.</dd>
  <dd>A plain list with no bullets or sequence numbers.</dd>

  <dt>Ordered</dt>
  <dd>A simple list with sequence numbers or letters.</dd>

  <dt>Description</dt>
  <dt>Definition</dt>
  <dd>A list with terms and definitions.</dd>
</dl>
```

![A description list](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_4/lists-overview-03.png)

- The 1st grouping has 1 term and 2 definitions
- The 2nd grouping has 1 term and 1 definition
- The 3rd grouping has 2 terms and 1 definition