## The types of `input`

Most controls are `<input>` elements. While some widgets look similar from browser to browser (eg. `text` `email` and `tel`), others differ greatly (`text` `submit` `checkbox`)

### What are the kinds of `type` attributes available?

HTML5 has tripled the number of `type` attributes available. Here are the most common ones:



#### What is `text` type?

`text` creates a simple text entry field where a user can enter any text they wish. The developer should almost always validate the input.

The `maxlength` attribute specifies the maximum length of the input.

<form action="#" method="post">
  <fieldset style="border: none">
    <label>
      <strong>First Name</strong>
      <input type="text" name="first_name" placeholder="Tom" />
    </label>
  </fieldset>
</form>


```html
<form action="#" method="post">
  <fieldset>
    <label>
      First Name
      <input type="text" name="first_name" placeholder="Tom" />
    </label>
  </fieldset>
</form>
```



#### What is `password` type?

`password` also creates a text entry field, except any text is replaced with dots. This is usually used to enter password or other sensitive data. Typically we remove the `value` attribute for this type.

<form action="#" method="post">
  <fieldset style="border: none">
    <label for="password"><strong>Password</strong></label>
    <input type="password" name="password" id="password" value="some-password" size="35" />
  </fieldset>
</form>

```html
<form action="#" method="post">
  <fieldset>
    <label for="password">Password</label>
    <input type="password" name="password" id="password"
           value="Not-good-password" size="35" />
  </fieldset>
</form>
```



#### What is `email` type?

Requires an email address entry into a text field. Browsers using `email` attempt to stop incorrect email formatting but the developer should validate the data too. 

<form action="#" method="post">
  <fieldset style="border:none">
    <label>
      Email
      <input type="email" name="email" placeholder="username@domain" />
    </label>
  </fieldset>
</form>

```html
<form action="#" method="post">
  <fieldset>
    <label>
      Email
      <input type="email" name="email" placeholder="username@domain" />
    </label>
  </fieldset>
</form>
```



#### What is `tel` type?

`tel` requires a telephone number entry. Browsers however will not validate the input because phone numbers differ so much across the globe. 

<form action="#" method="post">
  <fieldset style="border: none">
    <label>
      Phone
      <input type="tel" name="phone" placeholder="(###) ###-####" />
    </label>
  </fieldset>
</form>

```html
<form action="#" method="post">
  <fieldset>
    <label>
      Phone
      <input type="tel" name="phone" placeholder="(###) ###-####" />
    </label>
  </fieldset>
</form>
```



#### What is `checkbox` type?

`checkbox` allow the user to tick off zero or more yes/no type questions.

- `value` attribute is used here as a value that the form sends to the server if the checkbox is checked. each checkbox value should have a different name
- The `checked` attribute is Boolean that pre-selects checkboxes. 
- `name` attribute gives a name to a group of checkboxes.

- to select checked elements in CSS, use the `:checked` pseudo class, which will allow you to alter the appearance of a checked checkbox or radio button. Note that `:checked` will not look for the `checked` attribute but instead selects based on the state of the checkbox.
- When a checkbox is checked you can choose to send `name=value` pairs to the server or send `name` by itself. Without a `value` it will default to `name=on`

- in the below example the `Sort search results` checkbox won't be sent to the server because it isn't checked. The `Search on Google` will be sent as it is `checked`. 
- Since it has `name=value` pairs it will be sent as `choice=google`. If you remove the `value` attribute it will send `choice=on` which is often simpler
- Use the format that the server side code expects to receive. 

<form action="#" method="post">
  <fieldset style="border: none">
    <label>
      <input type="checkbox" name="choice" value="search" />
      Sort search results
    </label>
		<label>
      <input type="checkbox" name="choice" value="google" />
      Search on Google
    </label>
  </fieldset>
</form>

```html
<form action="#" method="post">
  <fieldset>
    <label>
      <input type="checkbox" name="search" />
      Sort search results
    </label>
    
		<label>
      <input type="checkbox" name="choice" value="google" checked />
      Search on Google
    </label>
  </fieldset>
</form>
```

#### What is `radio` type?

`radio` lets the user select either none or 1 option from a list. Unlike check boxes a user can only select 1 radio button from a set. Radio buttons work best with short lists. 5-8 items are too much for the developer and user. Opt for using the `select` control instead when you have lots of options to choose from.

Similar to checkboxes: 

- `value` attribute defines the value of this item that's sent to the server. Each value name should be different.
- `checked` marks the default radio button. Use the pseudo class `:checked` to style the `:checked` button in CSS.
- If selecting a radio button is optional, don't use the `checked` or `required` attributes. 
- If there is no default radio button use the `required` attribute on all radio buttons to force the user to select at least 1 button
- `name` groups related radio buttons together

```html
<form action="#" method="post">
  <fieldset>
    <label>
      <input type="radio" name="color" value="red" />
      Red
    </label>
    
    <label>
      <input type="radio" name="color" value="green" checked />
      Green
    </label>
  </fieldset>
</form>
```

<form action="#" method="post">
  <fieldset style="border: none">
    <label>
      <input type="radio" name="color" value="red" />
      Red
    </label>
    <label>
      <input type="radio" name="color" value="green" checked />
      Green
    </label>
  </fieldset>
</form>

#### What is `submit` type?

`submit` creates a button when clicked sends the contents of the form to the server. `<form>`'s ` action` attribute usually contains the URL of the server but this can be overridden using `formaction`.

```html
<form action="#" method="post">
  <fieldset>
    <input type="submit" value="Send" />
  </fieldset>
</form>
```

<form action="#" method="post">
  <fieldset style="border: none">
    <input type="submit" value="Send" />
  </fieldset>
</form>

#### What is `reset` type?

To reset the contents of a form to its default values use the `reset` type, which creates a button for you. Note that it doesn't send a request to the server.

```html
<form action="#" method="post">
  <fieldset>
    <input type="reset" value="Clear Form" />
  </fieldset>
</form>
```

<form action="#" method="post">
  <fieldset style="border: none">
    <input type="reset" value="Clear Form" />
  </fieldset>
</form>

#### What are the other `type` attributes?

Refer to the [MDN Documentation](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) for the complete list of `<input>` attributes. Look them up when you need them.
