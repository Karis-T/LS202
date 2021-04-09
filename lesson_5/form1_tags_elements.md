## Form tags

Forms are fundamental to HTML and are the point where backend and frontend development come together. Forms are how we collect user information and there are so many ways to do so, which is why we have so many different types of forms, controls and attributes to describe their characteristics.

Forms can:

- displays information to the user
- requests updates
- performs basic validation of information entered by user
- sends form data to the server

Form's cannot: 

- update information on the server and needs the help of back-end software (eg. ruby program) to accept the data from a browser and manipulate it in some way. 
- pre validate a form before sending it to the server- that's typically the work of JavaScript. JS is commonly used by most web apps.

### what is the `<form>` tag and why is it important?

 `<form>` is the parent tag that contains all form tags. It lets the browser know where and how to send data. `form`s most important attributes are `action` and `method`

A form must contain at least one: 

- `<input>`
- `<textarea>`
- `<select>`

element otherwise it's useless. **Control, widget** or **input** are the informal terms that are used to refer to any of the above tags. 

#### What does the `method` attribute do?

`method` attribute tells the browser whether to use HTTP `GET` or HTTP `POST` methods when it sends data to the server.

- use `method="get"` for requesting info from the server
- use `method="post"` is for updating data on the server

while HTTP allows you to use other methods, HTML restricts you to either `GET` or `POST`. To gain access to additional HTTP methods you must use JS or a backend app.

#### What does the `action` and `formaction` attributes do?

`action` contains the URL that the browser sends its requests to. To override`action` we can use `formaction` attribute via individual action items (such as `button` or `input type="submit"` elements)

### why is the `<fieldset>` important?

Rendered by most browsers as a border, `<fieldset>` is an optional tag that groups related form content together. While the border can be removed using CSS, its valuable for providing semantic data to the browser and it doubles as a selector for styling.

```html
<form action="/login" method="post">
  
  <fieldset>
    <input type="text" name="username" />
    <input type="password" name="password" />
  </fieldset>
  
  <fieldset>
    <input type="submit" value="Save" />
    <input type="submit" value="Forgot Password" formaction="/forgot" />
  </fieldset>
  
</form>
```

multiple `<fieldset>` elements contained within a form.

### what is the `<input>` tag and why is it important?

`input` is a self closing tag and it is the mechanism that enables users to send information to the app on the server. 

```html
<input type="text" name="city" />
<input type="password" name="password" />
<input type="submit" value="Save" />
```

### What is the `<label>` tag do?

1. `<label>` tag associates some text with an input field:

   ```html
   <label for="phone">Phone</label>
   <input type="text" id="phone" name="phone_number" />
   ```

   associating the text `Phone` with the `phone_number` field. To associate the 2 together the `for` and `id` attribute are used. This format allows the use to click on the label and make the cursor jump to the field.

   

2. `<label>` tags can also function as containers:

   ```html
   <label>
     Phone
     <input type="text" name="phone" />
   </label>
   ```

   this container style is easier to use by removing the `for` and `id ` attributes. Styling is more difficult however with this format and in some cases the association version must be used instead.

#### What does a form example look like?

```html
<form action="#" method="post">
  <fieldset>
    <h4>Log In</h4>
    <label for="username">Username</label>
    <input type="text" name="username" id="username" />
    <label for="password">Password</label>
    <input type="password" name="password" id="password" />
    <input type="submit" value="Log In" />
    <input type="submit" value="Delete account"
           formaction="/account/delete" />
    <input type="submit" value="Forgot password"
           formaction="/account/password" />
    <input type="reset" value="Reset" />
  </fieldset>
</form>
```

with a single form field container:

<form action="#" method="post">
  <fieldset>
    <h4>Log In</h4>
    <label for="username">Username</label>
    <input type="text" name="username" id="username" />
    <label for="password">Password</label>
    <input type="password" name="password" id="password" />
    <input type="submit" value="Log In" />
    <input type="submit" value="Delete account"
           formaction="/account/delete" />
    <input type="submit" value="Forgot password"
           formaction="/account/password" />
    <input type="reset" value="Reset" />
  </fieldset>
</form>

note: `formaction` attribute associated with the `delete account` button and `forgot password` button allows us to use the same form a do 3 different actions. If you click on either button, the browser will send the form info to the address specified in the `formaction` otherwise it heads to the address in the `action` attribute.



```html
<form action="#" method="post">
  <fieldset>
    <h4>Log In</h4>
    
    <fieldset>
      <label for="username">Username</label>
      <input type="text" name="username" id="username" />
    </fieldset>
    
    <fieldset>
      <label for="password">Password</label>
      <input type="password" name="password" id="password" />
    </fieldset>
    
    <fieldset>
      <input type="submit" value="Log In" />
      <input type="submit" value="Delete account"
             formaction="/account/delete" />
      <input type="submit" value="Forgot password"
             formaction="/account/password" />
      <input type="reset" value="Reset" />
    </fieldset>
    
  </fieldset>
</form>
```

```css
fieldset {
  border: none;
}
```

with multiple form field containers and border removed in CSS:

<style>
  fieldset{
    border: none;
  }
</style>
<form action="#" method="post">
  <fieldset>
    <h4>Log In</h4>
    <fieldset>
      <label for="username">Username</label>
      <input type="text" name="username" id="username" />
    </fieldset>
    <fieldset>
      <label for="password">Password</label>
      <input type="password" name="password" id="password" />
    </fieldset>
    <fieldset>
      <input type="submit" value="Log In" />
      <input type="submit" value="Delete account"
             formaction="/account/delete" />
      <input type="submit" value="Forgot password"
             formaction="/account/password" />
      <input type="reset" value="Reset" />
    </fieldset>
  </fieldset>
</form>
### What is the `<textarea>` element?

basically a textbox - allows multiple lines of text.

- `text` type inputs ignore carriage returns, newlines and other whitespace characters. `textarea` retains them for formatting the lines and paragraphs. 
- The `value` attribute isn't used to display text, instead you must enter all the text between the opening and closing `textarea` tags
- code the `<textarea>` tags on the same line unless the content contains new lines

```html
<form action="#" method="post">
  <fieldset>
    <label>
      Comment
      <textarea name="tweet">I got 20% off my first purchase!</textarea>
    </label>
  </fieldset>
</form>
```

<form action="#" method="post">
  <fieldset>
    <label for="tweet" style="display: block">Comment</label>
    <textarea name="tweet" id="tweet" rows="3" cols="30">I got 20% off my first purchase at joesburgers.com! You can too!</textarea>
  </fieldset>
</form>

#### what are Rows and Cols?

Control the height and width of a `textarea` element with `rows` and `cols` attributes  respectively. 

- like the `size` attribute, measurements are approximate and may display more or less lines than requested. 
- They can also be overridden by `height` and `width` CSS properties
- `rows` represents the number of visible lines - not max no. of lines. Vertical scrolling is enabled when the no. of lines exceeds the no of `rows` 
- most browsers support `textarea` resizing which can be done using the triangle at the bottom right. This can be disabled in CSS with the `resize` property 

### What does the `<select>` element do?

creates a drop-down list of options that can select zero or more items.

-  `select` has 2 child elements `optgroup` and `option`
- `name` attribute is used like other form elements use it

#### How does the `<option>` element work?

`<option>` elements display the options available to the user and is also sent to the server (which may be 2 different things)

- A single `option` represents one choice a user can make.
- `select` is useless without `option`
- `value` is the data that's sent to the server
- if `value` is not available the browser sends the text between the `option` tags 
- for helpful, unselectable text like "Choose one" use the attributes `disabled` and `selected`. It works like a placeholder attribute 

```html
<form action="#" method="post">
  <fieldset>
    <label>
      Colors
      <select name="color">
        <option value="" disabled selected>Choose one</option>
        <option value="#f00">Red</option>
        <option value="#0f0">Green</option>
        <option value="#00f">Blue</option>
      </select>
    </label>
  </fieldset>
</form>
```

<form action="#" method="post">
  <fieldset>
    <label>
      Colors
      <select name="color">
        <option value="" disabled selected>Choose one</option>
        <option value="#f00">Red</option>
        <option value="#0f0">Green</option>
        <option value="#00f">Blue</option>
      </select>
    </label>
  </fieldset>
</form>

For selecting *multiple options* using `ctrl`/`cmd` click, add `multiple` to the attributes in the `select` tag. If you specify `multiple` you can also control the `size` of the selection box/

```html
<form action="#" method="post">
  <fieldset>
    <label>
      Choose Your Favorite Movies
      <select name="favorites" multiple size="4">
        <option value="" disabled selected>Select One or More</option>
        <option>2001: A Space Odyssey</option>
        <option>Arrival</option>
        <option>Close Encounters of the Third Kind</option>
        <option>District 9</option>
        <option>Guardians of the Galaxy</option>
        <option>Interstellar</option>
        <option>Serenity</option>
        <option>Silent Running</option>
      </select>
    </label>
  </fieldset>
</form>
```

<form action="#" method="post">
  <fieldset>
    <label style="display: block;"><strong>Choose Your Favorite Movies</strong></label>
      <select name="favorites" multiple size="4">
        <option value="" disabled selected>Select One or More</option>
        <option>2001: A Space Odyssey</option>
        <option>Arrival</option>
        <option>Close Encounters of the Third Kind</option>
        <option>District 9</option>
        <option>Guardians of the Galaxy</option>
        <option>Interstellar</option>
        <option>Serenity</option>
        <option>Silent Running</option>
      </select>
  </fieldset>
</form>

