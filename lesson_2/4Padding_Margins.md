## How do Padding and Margins work?

### What is the difference between padding and margins?

Even though both are whitespace that surrounds an element, each have their differences:

###### padding:

- lies inside the border
- typically opaque
- apart of the clickable area of an element
- border is part of the clickable are

###### margins:

- lie outside the border
- typically transparent
- spacing between adjacent elements
- margin is not apart of the clickable area

#### How do padding and margins relate to backgrounds?

Even if you haven't explicitly set a margin, you always have one and its recognized by the browser. 

The background of an element is made up of padding. But because element margins are transparent you can see through the margins and see the container behind it.

#### How do top and bottom margins and padding work on inline elements?

when it comes to spacing, the browser doesn't use top and bottom margins and padding for `inline` elements. Regardless of how big top and bottom margins are, they don't affect where the element's content is placed nor the content surrounding it.

![image-20210328152548203](C:\Users\Karis\AppData\Roaming\Typora\typora-user-images\image-20210328152548203.png)

Here even though the green element has a margin of 40px, its transparent, so you can see the element's container (which is pink) sitting in the background. 

#### What is 'Margin Collapse'?

the margins between two block stacked on top of each other will collapse and only the bigger margin is chosen of the two.

![image-20210328152041157](C:\Users\Karis\AppData\Roaming\Typora\typora-user-images\image-20210328152041157.png)

The example has a `bottom-margin` of `30px` and a `top-margin` of `32px`. This means the `top-margin` is favored and only `32px` is displayed between them.

Only top and bottom margins suffer margin collapse - **Left and right margins are fine.** And **padding doesn't collapse.**

### Should I use padding or margins?

While there is no one correct way as a best practice for **elements**:

- use margins as **space between elements**
- use padding for **visible / clickable area of an element**

For **containers:**

- padding for **horizontal separation** between the content
- margins for **vertical distance**

Another technique:

- use margins everywhere **except**:
  - when you want to change the height / width of a border
  - adjusting background visibility around an element
  - altering the amount of clickable area
  - avoiding margin collapse
  - when you want horizontal spacing left or right of an inline element
  - padding is needed for left and right sides of a container from its content and margins as a vertical gap