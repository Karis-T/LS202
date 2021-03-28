## How is everything a Box?

In word processing software each character is output one at a time from left to right forming a word. If a word doesn't fit it drops to a new line and word processing begins again from left to right.

Browsers deal with more than just words, including images media players and containers which we'll call **elements**.

The browser needs to determine how much space is required both horizontally and vertically to draw the object. The browser uses its defaults but also your css to calculate these dimensions. 

The most important takeaways from this are:

- every single element and text character requires a box-shape segment of the page.
- Browsers calculate the boxes dimensions by using browser default and CSS. 
- the term **box model** defines how browsers calculates the box size of an element.

### How do widths & heights work in the Box Model?

All elements consist of a `height` and a `width`. All elements by default have a `display` property value of`inline-block`: this means that all elements are laid out side by side up to the browsers page width. If it doesn't fit it drops down to a new line.

Note: actual alignment will vary based on the CSS settings of each rectangle.

![Box layout at 800 pixels width](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_2/everything-a-box-1.png)

### What are the Box Properties and how do they work? 

![Chrome's box model](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_2/chrome_box_model.png)

this diagram:

- has a **content area** of 928 width and 168 height
- 10px top and bottom **padding**. 20px left and right **padding**
- **border** 1px thick
- 28px bottom **margin** (the left, right and top margins are 0)



Every box has the following CSS properties: (some may be ignored by the browser)

#### `width` & `height` 

these properties calculate how much width and height is needed for the **content area** of the box. This may / may not include padding and borders. Width and height is usually calculated automatically by browsers.

#### `padding` 

the space that **sits between the content area and the border** of a box. It's usually opaque and hides what it overlaps. It also *separates the content from its border*

#### `border` 

This is the boundary that **sits outside the padding**

#### `margin`

A transparent space that **sits outside the border** and provides a *separation between elements*

#### `display`

How an element is laid out relative to its neighbors. 