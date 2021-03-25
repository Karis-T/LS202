#### Overall Our code should be:

- **Well organized so** it's easy to read, edit and maintain over time
- **Modular and flexible** and encourage code reusability
- **Consistent** whether a single or multiple people write the code

## Best Practices for Writing Code

### HTML Coding Practices

#### What are Standards-Compliant Markup and why should we use it?

Make sure your syntax is correct and validate your code often with W3C. 

```html
<!--- bad code missing closing tag and uses id attribute--->
<p id="intro">The caramel apple cider is delicious.

<!--- good code closes element and uses class attribute--->  
<p class="intro">The caramel apple cider is delicious.</p>
```

#### Why should we make use of Semantic Elements?

Be sure to always use semantic code where possible. It allows you to structure more easy to read code and it creates a more usable and easy to access website.

#### Why do we use Proper Document Structure?

When writing html be sure to always include the `<!DOCTYPE html>` ,`<html>`, `<head>`, and `<body>` elements. Without them it's not guaranteed that all browsers will be able to render the html properly.

#### How do we keep the Syntax Organized?

- use lowercase letter for element names, attributes and values
- be sure to indent nested elements
- use double quotes instead of single
- omit values of Boolean attributes

#### Why should we use Practical ID & Class Values?

Should the style of an element ever need to be changed we cannot rely on style based classes and ids. This is why we should always name based on the content not the style.

#### Why should we use Alternative Text Attribute on Images?

including alternative text for images allows screen readers and assistive tech understand the image and its context. The alt description should also be very relevant to what the image is. If the image doesn't have meaning it should be apart of the CSS background image and not an <img> element.

#### Why separate Content from Style?

Don't create inline styles in the HTML - it can cause longer load times, cause inconsistency and confusion for designers and developers down the line. Opt for external style sheets to keep all you css in one place.

#### Why shouldn't we use `div`?

It's easy to get carried away with using div elements to the point where you dont know what it is anymore. Try to avoid this by tying multiple styles to a single element and use HTML5 structure like <article>:

```html
<!--- confusing --->
<div class="container">
  <div class="article">
    <div class="headline">Headlines Across the World</div>
  </div>
</div>

<!--- good --->
<div class="container">
  <article>
    <h1>Headlines Across the World</h1>
  </article>
</div>
```

#### Why continuously refactor our code?

If you're editing an existing page or building a new one, remember to remove old code and styles that isn't necessary anymore to keep code lean and uncluttered.

### CSS Coding Practices

#### How should we Organize Code with Comments?

CSS files can grow very large and as such we need a naming system to keep track of all styles available. If you wish you can build a table of contents at the top of the page.

 ```
too vague:
header { ... }
article { ... }
.btn { ... }

good use of comments:
/* Primary header */
header { ... }

/* Featured article */
article { ... }

/* Buttons */
.btn { ... }
 ```

#### What are Proper Class Names and why should we use them?

Create lowercase, content based naming for classes. Their names should not pertain to appearance and should not include uppercasing nor underscores.

```css
/*no*/
.Red_Box { ... }
/*yes*/
.alert-message { ... }
```

#### How do we Build Proficient Selectors?

Weighting can be an issue and if mishandled can break the cascade. Avoid using #ids and only nest selectors 2 or 3 levels deep, not more than that. Also remove location based selectors where possible.

```css
/* remove unnessary ids and location qualifiers */
#aside #featured ul.news li a { ... }

/* this is cleaner and more modular */
.news a { ... }
```

#### Why should we use specific classes when necessary?

Sometimes the chain of specificity is so long, convoluted and affects performance. We are better off creating a single class devoted to that one element we want to select:

```css
/* too convoluted and hurts performance */
section aside h1 em {
  ... 
}

/* better */
.text-offset { 
  ... 
}
```

#### Why use Shorthand Properties, Values and Hex Color Values?

For properties one good way of reducing the amount of code you write is avoid the longform of a property and embrace its shorthand version. If we are only setting one value however its a good idea just to use that specific selector:

```css
img {
  margin: 5px 10px;
}
button {
  padding-left: 20px;
}
```

For Hex Color values reduce the duplication in your code by trimming it down to 3 digits instead of 6 when necessary and always use lowercase values:

```css
.module {
  background: #ddd;
  color: #f60;
}
```

#### Why drop units from zero Values?

Zero is always zero no matter what unit of measurement you use. It's a very easy way to reduce the amount of code you write.

#### Why should we group / Align Vendor Prefixes?

Be careful and neat about how your code sits when adding Vendor Prefixes so its easier to see, read and maintain. Try to line up everything like so:

```
div {
background: -webkit-linear-gradient(#a1d3b0, #f6f1d3);
background:    -moz-linear-gradient(#a1d3b0, #f6f1d3);
background:         linear-gradient(#a1d3b0, #f6f1d3);
-webkit-box-sizing: border-box;
   -moz-box-sizing: border-box;
        box-sizing: border-box;
}
```

#### How do we Modularize styles for reuse?

styles assigned to classes should be modular and available for all elements to share. Try to avoid duplication in your code and come up with a more appropriate naming system that can be shared between elements who need the same styling:

```css
/* too much duplication, not modular*/
.news {
  background: #eee;
  border: 1px solid #ccc;
}
.events {
  background: #eee;
  border: 1px solid #ccc;
}

/* more reusable and can be applied to both elements*/
.feat-box {
  background: #eee;
  border: 1px solid #ccc;
}
```