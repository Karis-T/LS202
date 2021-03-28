## How Do Dimensions work in CSS?

### What is the difference between absolute vs relative Units?

Absolute measures don't change depending on circumstances. A more modern unit is the *story* or *floor* used to give the height of buildings: they are not all the same height.

#### How do Absolute units work?

> physical measurements based on the medium they're used in. Relative units are anchored to a physical ones. 

Pixels are the most significant out of the absolute units and in CSS they are much more than a single spot of light on your display. Put simply pixels on a desktop are not the same size as pixels on a phone. CSS combats this by making a distinction between the 2: physical pixels and CSS reference pixels.

reference pixel size is relative to display size. So if display has 96ppi 1 physical pixel will be used,  but if its 192ppi there will be 4 physical pixels to accommodate the high res display. This is so images will be about the same size on each display.

CSS defines the reference pixel based on the **angular** diameter of a CSS pixel **as viewed from the typical viewing distance (TVD) for the display**.  so if we place both screens at the appropriate TVD, that 200x200 pixel image appears to be the same size 

#### What are some other Absolute Units?

due to too much variation between pixels and real measurements like inches or millimeters, developers tend to stay away from them unless they need something 'life size.'

#### How do Relative Units Work?

> a measurement that depends on another distance. It could be the size of a character, a line height or the size of viewport.

ems, rems and percentages are some of the more popular relative elements.

###### What are Ems vs Rems?

> `em` and `rem` are used to create scalable layouts. `rem` are used as the initial font size of the root element. (eg. 1 rem = 16px default browser size). `em` is the calculated `font-size` of the element. if used on the `font-size` itself it represents the *inherited* font size of the element.

- `em` is a calculated font size which is the height of the **current** font in pixels.
  - ems compound each time you use it. It reassigns the value as the current value.

- `rem` is a root font size which is height of the **base** font of the `html` or `body`.
  - rems are consistent throughout the document

if calculated font is 20px and root font is 16px:

- 1.5 em is 30px (20 x 1.5)
- 1.5 rem is 24px (16 x 1.5)

use pixels to specify the root font otherwise there may be unexpected results (element overflow, overlapping and rearranging on the page)

```html
<h1>Using `em` Units</h1>
<div class="a-em">
  1em == 1 * 24px == 24px
  <div class="b-em">
    1.5em == 1.5 * 24px == 36px
    <div class="c-em">
      2em == 2 * 36px == 72px
      <div class="a-em">
        1em == 1 * 72px == 72px
      </div>
    </div>
  </div>
</div>

<hr />

<h1>Using `rem` Units</h1>
<div class="a-rem">
  1rem == 1 * 24px == 24px
  <div class="b-rem">
    1.5rem == 1.5 * 24px == 36px
    <div class="c-rem">
      2rem == 2 * 24px == 48px
      <div class="a-rem">
        1rem == 1 * 24px == 24px
      </div>
    </div>
  </div>
</div>
```

![Ems and Rems](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_2/measurement-units-01.png)

Some older browsers don't recognize rems so you must support them with fallback units like pixels. f you must use fallbacks, assume `16px` font-size is your best bet.

```css
p {
  font-size: 20px; font-size: 1.25rem;
}
```

###### How do Percentages work?

> only length values can be inherited, not percentage ones. Although percentages are used in properties that accepts length values, they are not length values.

Percentages are used to express dimensions as a fraction of the containers `width` / `height`. eg. If you put either a `block` or `inline-block` inside a container and set the `width` to 50%, the element's width is 50% of the container.

`width` and `height` have no effect on `inline` elements.

###### How does Auto work?

Auto is not a length but it can be used when we want the browser to decide the height and width for us. The best times to use `auto` is:

- as a `width` and `height`, where the browser will try to fit the element (including  margins) inside the container.
- *left or right* `margin` values of `block` elements ONLY. This is where the browser will slide the element way *right or left* inside its container.
- top or bottom `margin` values are equal to `0`
- `padding` doesn't use `auto` values
- `auto` doesn't work on `inline-block` or `inline` elements 

![width: auto](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_2/measurement-units-03.png)

```css
#center-margin-auto-center {
  margin: 10px auto;
  /* margin: XXX auto; */
}

#center-margin-auto-right {
  margin: 10px 10px 10px auto;
}
```

`auto` and `100%` are not the same:

- `width: auto` the browser attempts to squish the element (including margins, border and padding into the container).
-  `width: 100%` won't consider the element's `margin` and if you set it to `content-box` it wont consider its `padding` or `border` either. The element might extend past the container.

![width: auto vs width: 100%](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_2/measurement-units-02.png)

```css
#auto-width-auto {
  width: auto;
}

#auto-width-100-border {
  box-sizing: border-box;
  width: 100%;
}

#auto-width-100-content {
  box-sizing: content-box;
  width: 100%;
}
```

#### What are zero lengths?

Standard CSS style prescribes we omit the unit name when we use `0` in our code.

#### How do we Mix Units?

You can freely mix units wherever you choose on a page. However mixing units can cause problems when you need to figure out what the final display length will be.

```html
<div class="a">
  <div class="b"></div>
  <div class="c"></div>
</div>
```

```css
.a {
  width: 500px;
}

.b {
  display: inline-block;
  margin: 0 50px;
  width: 25%;
}

.c {
  display: inline-block;
  margin: 0 1rem;
  width: ???;
}
```

Using `border-box` can be helpful in a situation like this (if you're not using left / right margins on the inner boxes)

#### When do we use different units?

- use **absolute units** (pixels) occasionally for:
  - root font size
  - image widths and heights
  - top and bottom margins / padding (sometimes left / right margins and padding)
  - fixed width / height containers (eg. nav sidebars)
  - border widths

- use **relative units** liberally for:

  - rems for fonts, use ems or pixels as a backup. *root font should be pixels*
  - avoid compounding font sizes if using ems
  - use rems / ems / pixels for left and right margins and padding
  - use `%`  for elements that are proportional to the width and height of its container. `%` work great for container dimensions and come in handy when you need the page to grow and shrink as the browser width changes. 
  - use `auto` with `width` and `height` to let browser calculate the best value
  - use `auto` for left and right block element margins so its justified appropriately (left, right or center) within its container. 

  You can break any of these rules when you see fit.