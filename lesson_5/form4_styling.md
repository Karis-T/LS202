## Form Layout

```css
/* Eliminate margins and padding on everything */
.styled-form * {
  margin: 0;
  padding: 0;
}

/* Grey box and default font for fieldsets */
.styled-form fieldset {
  background-color: #ececec;
  border: 2px solid #999;
  box-sizing: border-box;
  color: #4d4d4d;
  font-family:
    myriad-pro, "Helvetica Neue", Helvetica, Roboto,
    Arial, sans-serif;
  padding: 1rem;
}

/* Custom appearance for labels */
.styled-form label {
  font-weight: bold;
  line-height: 1.5rem;
}

/* Custom appearance for input and select fields */
.styled-form input[type="text"],
.styled-form select {
  border: 1px solid #06c;
  border-radius: 4px;
  box-sizing: border-box;
  font: normal 1rem Helvetica, Arial, sans-serif;
  height: 40px;
  padding: 5px 8px;
}

/* More customization for select lists */
.styled-form select {
  -moz-appearance: none;
  -webkit-appearance: none;
  appearance: none;
  background-image:
    url("data:a_url_goes_here");
  background-position: 100% center;
  background-repeat: no-repeat;
  padding-right: 1.5rem;
}
```



![image-20210406203217333](C:\Users\Karis\AppData\Roaming\Typora\typora-user-images\image-20210406203217333.png)

- The three types of `background` properties provide the custom arrow and background for the select control (you should know how to do this)
- the background-image url loads and inline image showing the dropdown arrow. You will typically recieve a `data:` url to plug into the `url()` value
- `border-radius` allows you to round border corners according to its radius
- `appearance` allows you to turn off the default browser appearance of a widget (`select` in this case) (you should know how to do this)
- if you want to check what properties are supported by which browsers use [caniuse.com](https://caniuse.com/)
- `appearance` as of 2018, is experimental but 95% of browsers support accept the value of `none` when you use vendor specific names like `-webkit-appearance` and `-moz-appearance`

### top to bottom layout

```css
/* Added to end of file */
.top-to-bottom label,
.top-to-bottom input[type="text"] {
  display: block;
  width: 100%;
}
```

![image-20210406203245753](C:\Users\Karis\AppData\Roaming\Typora\typora-user-images\image-20210406203245753.png)

- convert the `label` and `input` items to block elements to make it look like a top to bottom form as shown above

### side by side layout

```css
/* Add to end of file */
.side-by-side label,
.side-by-side input[type="text"] {
  display: inline-block;
}

.side-by-side label {
  margin-right: 1rem;
  vertical-align: middle;
}

.side-by-side input[type="text"] {
  vertical-align: middle;
  width: 35%;
}
```

![image-20210406203305190](C:\Users\Karis\AppData\Roaming\Typora\typora-user-images\image-20210406203305190.png)

- to put the label and input side by side requires more css:
  - convert the `label` and `input` to `inline-block` for a side by side look
  - if you provide specific widths and heights and use `inline` display, the browser will ignore those dimensions
  - set the `width` of the `input` and `vertical-align` `label` and `input`



![image-20210406203324768](C:\Users\Karis\AppData\Roaming\Typora\typora-user-images\image-20210406203324768.png)

- if you add an extra label/input pair and the screen is large enough, all labels will appear in one row



![image-20210408154258350](C:\Users\Karis\AppData\Roaming\Typora\typora-user-images\image-20210408154258350.png)

- However if you resize the screen to a narrower width, the elements will wrap and the label will appear on top with its input on the next line.
- This is ugly and unhelpful and usually leads developers to wrap label / input pairs in `block` elements such as `div`. `block` containers ensures label / input pairs stay together

```html
<form action="#" class="styled-form side-by-side">
  <fieldset>
    <div class="keep-together">
      <label for="text_field">Input Field</label>
      <input type="text" name="text_field" id="text_field"
    </div>

    <div class="keep-together">
      <label for="another_field">Another Field</label>
      <input type="text" name="another_field" id="another_field"
    </div>
  </fieldset>
</form>
```

![image-20210406203427454](C:\Users\Karis\AppData\Roaming\Typora\typora-user-images\image-20210406203427454.png)

- The problem with this is that each `label` has a different width, so the inputs don't line up.
- Even if we try to put labels in one column and inputs in another it still creates readability, maintainability and alignment issues



### How to use Description Lists to align label/input pairs

While it may seem strange, description lists add semantic meaning to `label`s and `input`s. 

- labels are like terms and identify the controls for the user
- inputs are like the description definitions when text is entered into it
- They also provide additional tags for styling without altering your HTML

```html
<form action="#" class="styled-form side-by-side">
  <fieldset>
    <dl>
      <dt><label for="text_field">Input Field</label></dt>
      <dd><input type="text" id="text_field" name="text_field" /></dd>

      <dt><label for="another_field">Another Field</label></dt>
      <dd><input type="text" id="another_field" name="another_field" /></dd>
    </dl>
  </fieldset>
</form>
```

```css
.side-by-side input[type="text"] {
  width: 100%; /* Replaces 35% */
}

/* Add to end of file */
.side-by-side dl {
  font-size: 0;
}

.side-by-side dt,
.side-by-side dd {
  box-sizing: border-box;
  display: inline-block;
  font-size: 1rem;
  vertical-align: middle;
}

.side-by-side dt {
  padding-right: 1rem;
  width: 25%;
}

.side-by-side dd {
  width: 75%;
}
```

![image-20210406203447048](C:\Users\Karis\AppData\Roaming\Typora\typora-user-images\image-20210406203447048.png)



- if you want further flexibility divide each label/input pairs into separate lists so each pair has a different container. 
- This allows you to style related pairs together on one horizontal line (city, state zip)
- to do this add appropriate classes to the dl elements and style them 

![image-20210406203509046](C:\Users\Karis\AppData\Roaming\Typora\typora-user-images\image-20210406203509046.png)

- this above shows one `dl` per label/input pair. This allows us to treat each dl separately.
- having one `dl` per pair however makes it harder to create a horizontal layout where each `label` is the same size.
- `partial` class gives the `dl` basic `inline-block` styling
- the class name for each input gives us the `width` and other overriding properties like padding 
- typing lists like states are tedious and a good developer is a lazy developer.  [here](https://launchschool.com/gists/2424a869) is a list of all US states as `select` options.