## Get to Know CSS

### How do style sheets cascade from top to bottom?

#### What is the Cascade and why is it important?

All styles cascade from the top of a style sheet to the bottom where subsequent selected styles can override preceding ones. 

```css
/*The paragraph background will now be green. Font size stays the same*/

p {
  background: orange;
  font-size: 24px;
}

p {
  background: green;
}
```

###### What are Cascading properties?

This refers to the properties inside the selector where if we duplicate the property but change the last value, the last value will override the preceding one.

```css
/*The paragraph background will now be green.*/
p {
  background: orange;
  background: green;
}
```

### What is specificity and how is it calculated?

The 3 selectors type, class and id each holds a specificity weight and determines which one will take precedence over the other.

- The type selector has a low specificity weight 0-0-1
- The class selector has a medium specificity weight 0-1-0
- The id selector has a high specificity weight 1-0-0

```html
<p id="food">...</p>
```

```css
#food {
  background: green
}

p {
  background: orange
}
```

Despite the `p` following the `#food` selector, The background of the above HTML paragraph will be green. This is because id selectors have a higher specificity point weight than type selectors. This can lead to a lot of confusion so its important to know.

### How do we combine selectors to target specific elements or element groups?

When we combine selectors together to render more complicated backgrounds they should be read from right to left. 

```html
<div class="hotdog">
  <p>...</p>
  <p>...</p>
  <p class="mustard">...</p>
</div>
```

```css
.hotdog p {
  background: brown;
}
.hotdog p.mustard; {
  background: yellow;
}
```

- The rightmost selector is known as a *key selector*, which is the selector you are applying the styles to. 
- The leftmost selectors are prequalifiers to using the key selector. 

Because it's prequalified,  The first selector `.hotdog p` only selects the *paragraphs inside the hotdog class.*

The second selector `.hotdog p.mustard` only selects the *mustard paragraph inside the hotdog class*

<div style="border: 1px solid gray; padding: 1% 4% 2% 4%">
  <h6>What are Spaces within Selectors?</h6>
  <p>be careful with your space placement when combining selectors. The best practice is to not prefix a class selector with a type selector.We want to be able to select any element in a given class, not just one type. That being said ".hotdog .mustard" is a better practice</p>
</div>

###### How does Specificity Within Combined Selectors work?

```css
/*combined weight of 0-1-1*/
.hotdog p {
  background: brown;
}
/*combined weight of 0-2-1 = this one takes precedence*/
.hotdog p.mustard; {
  background: yellow;
}
```

Keep an eye on specificity weight to ensure the cascade doesn't break. The higher the weight the more likely it is to fail. Weighting takes precedence over cascade order.

### How do we use multiple classes on a single element for layering different styles for modular code?

One way to keep specificity weighting low is to create modularity using multiple classes. This allows your classes to have more reusability. 

```html
<a class="btn btn-danger">...</a>
<a class="btn btn-success">...</a>
```

```css
.btn {
  font-size: 16px;
}

.btn-danger {
  background: red;
}

.btn-success {
  background: green;
}
```

Above Using multiple classes both buttons have a font of 16px but have different classes devoted to different button events.

HTML elements can have multiple values by using a space as a separator between values. By doubling up classes we can then create a hierarchal class structure, keeping our code weights lean and reusable. 

### What are the different Color Values available to CSS?

#### Why are colors important in CSS?

All CSS colors are based on the sRGB (standard red green and blue) color space which are used by tvs and monitors. Colors are mixed together using RGB channels - creating millions of color combinations.

###### What are keyword colors?

keyword colors are color names that map to common colors (such as `red` `green` and `yellow`). They are determined by the [CSS Specification](https://www.w3.org/TR/css3-color/), and while easy to use there's only a limited amount available. 

###### What are hexadecimal colors?

hexadecimal colors are comprised of 6 hexadecimal digits with each pair of digits matching to red, green and blue channels. They are prefixed with a hashtag and if hexadecimals have repeating numbers they can be stated as 3 digits instead of 6. Although they are a little tricky to calculate, hexadecimals have been around for a long time and are a very popular format - with over 16.7 million colors available.  

```css
.count {
  background: #ff0;
}
```

###### ![Hexadecimal Color Syntax](https://learn.shayhowe.com/assets/images/courses/html-css/getting-to-know-css/hexadecimal-syntax.png)

###### What are RGB and RGBa colors?

RGB stands for Red Green and Blue and uses the rgb() or rgba() function. the function takes 3 integers ranging from 0 to 255 with each number represented by the red, green and blue channels respectively. RGB also supports an alpha channel with a range from 0 to 1 representing how transparent you want to object to be. RGB is quite a popular color value to work with.

```css
.count {
  background: rgba(255, 255, 0, 1)
}
```



###### What are HSL & HSLa colors?

HSL stands for Hue, Saturation and Lightness and uses the hsl() or hsla() function. It's indicated by 3 digits, with Hue ranging from 0 to 360 pertaining to the hue of the color. Saturation and lightness are percentages and indicate how saturated and how much white / black you'd like to add to the color. HSL also supports an alpha channel (a) which if included ranges from 0 to 1 and is usually stated as a decimal. Because it's newer, It's not often used as most prefer to work with RGB (or RGBa).

```css
.count {
  background: hsla(60%, 100%, 50%, 1)
}
```



### What are the different length values available to CSS?

###### Absolute vs Relative Lengths

- **Absolute Lengths:** Fixed, physical units of length such as inches or millimeters. The most popular absolute length is the pixel.
- **Relative Lengths:** Lengths that rely on the length of another measurement. They aren't fixed units.

###### What are Pixels?

There are 96 pixels per inch and great for starting out but due to the wide variety of devices and platforms and their inflexible nature they aren't relied on as much as they used to be.

```css
p {
  font-size: 14px;
}
```

###### What are Percentages?

A percentage is based on it's parent width. eg. 50% of parent's element's width. Percentages are very helpful for building the heights and widths of a webpage.

```css
.col {
  width: 50%;
}
```

###### What is em?

based on the element's font size. 1 em unit is equivalent to the font size you set. If you don't explicitly state the font size the em unit will be relative to the closest parent element with an explicit font size. It's helpful for text styling, paddings and margins.

```css
.banner {
  font-size: 14px;
  width: 5em;
}
```