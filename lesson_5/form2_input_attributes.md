## What are some of the `input` Attributes?

the `<input>` element has a bunch of attributes. Here are the most common ones worth knowing. 

#### What does the `type` attribute do?

`<input>` *must* use the `type` attribute which contains vast amount of values new to HTML5 that indicate the type of widget desired. (eg. `type="text"` gives us a text field, whereas `type="submit"` gives us a submit button to send the form to the server) 

#### What does the `name` attribute do?

`<input>` also *must* have a `name` attribute. The browser uses `name` to identify each item in the form, and back-end apps use `name` to find its value.

- `name` attribute gives a name to a group of checkboxes.
- When a checkbox is checked you can choose to send `name=value` pairs to the server or send `name` by itself. Without a `value` it will default to `name=on`

#### What does the `value` attribute do?

The meaning of the `value` attribute changes depending on which `type` uses it. 

- text-based types including `text` `email` and `number` - `value` represents the default text displayed in the field. If there is no `value` the browser uses an empty string. use `value` in this context if its been retrieved from a database or provided by the user during the session.

  ```html
  <input type="tel" name="phone" value="503-555-1212" />
  ```

  <form action="#" method="post">
    <fieldset style="border: none">
      <label>
        Phone
        <input type="tel" name="phone" value="503-555-1212" />
      </label>
    </fieldset>
  </form>

-  `checkbox` and `radio` types use `value` to represent the value of the button that the form will submit to the server. While `radio` `value` attribute is optional it can lead to unexpected results, always use a `name` attribute on all buttons that belong together. 

  ```html
  <input type="radio" name="color" value="blue" checked />
  ```

<form action="#" method="post">
  <fieldset style="border: none">
    <label>
      <input type="radio" name="color" value="red" />
      Red
    </label>
    <br />
<label>
  <input type="radio" name="color" value="blue" checked />
  Blue
</label>
<br />
<label>
  <input type="radio" name="color" value="green" />
  Green
</label>
  </fieldset>
</form>

- button types including `submit` and `reset` use `value` for the label that appears on the button. Note that `type="button"` is not supported- use the `<button>` element instead.

  ```html
  <input type="submit" value="Save" />
  ```

  <form action="#" method="post">
    <fieldset style="border: none">
      <input type="submit" value="Save" />
    </fieldset>
  </form>

#### What does the `formaction` attribute do?

`<form>`'s ` action` attribute usually contains the URL of the server but this can be overridden using `formaction`.  `formaction` attribute associated with different buttons allows us to use the same form a do different actions. If you click on either button, the browser will send the form info to the address specified in the `formaction` otherwise it heads to the address in the `action` attribute.

#### What do `size` and `maxlength` attributes do?

controls the `size` of an input element using character units. You can override this with CSS `width` property but character measurements aren't supported. Note that `size` is an only approximation and more or less characters may be displayed.

`maxlength` is similar to `size` except it limits the maximum length of input values. This value can be more or less than the `size` value. 

```html
<form action="#" method="post">
  <fieldset>
    <label>
      Phone
      <input type="tel" name="phone" size="10" maxlength="16" />
    </label>
    <br />
    <label>
      Cell Phone
      <input type="tel" name="cell-phone" size="20" maxlength="40" />
    </label>
  </fieldset>
</form>
```

![size and maxlength attributes](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_5/input-attributes-04.png)

#### What is the `placeholder` attribute?

Displays some greyed-out text when the field is empty to help describe the expected input. This attribute is available for *most* text based input types.

Don't use placeholders as a substitutes for labels as it prevents screen readers from doing their job. If you're forced to only use placeholders only, include the label anyways and hide it using CSS. 

```html
<form action="#" method="post">
  <fieldset>
    <label>
      Phone
      <input type="tel" name="phone" placeholder="###-###-####" />
    </label>
  </fieldset>
</form>
```

![placeholder attribute](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_5/input-attributes-05.png)

#### How does the `disabled` attribute work?

Greyed out input rendered by a browser that prevents users from entering anything. Most web apps handle the `disabled` attribute through a program, usually when the app generates the HTML or dynamically with JS. You must know `disabled` exists to write HTML for a program that expects `disabled` inputs on the original form.   

`disabled` also enables the CSS pseudo-class `:disabled` for styling. 

```html
<form action="#" method="post">
  <fieldset>
    <label>
      Email
      <input type="email" name="email" value="xyz@example.com" disabled />
    </label>
    <br />
    <input type="submit" value="Save" disabled />
  </fieldset>
</form>
```

![disabled attribute](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_5/input-attributes-06.png)

#### What is the `required` attribute?

The browser won't let you submit the form until the user completes the `required` fields. `required` also enables the CSS pseudo-class `:required` for styling.  

```html
<form action="#" method="post">
  <fieldset>
    <label>
      Home Phone
      <input type="text" name="home_phone" required />
    </label>
    <br />
    <label>
      Business Phone
      <input type="text" name="business_phone" />
    </label>
    <br />
    <input type="submit" value="Save" />
  </fieldset>
</form>
```

```css
input:required {
  background-color: yellow;
}
```

![reuqired attribute](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_5/input-attributes-07.png)

#### what is the `autocomplete` attribute?

Turn autocomplete `on` or `off` to enable or prevent the browser from  storing data and using it to execute its `autocomplete` features. This feature is common on mobile devices but can be unhelpful so it can be explicitly turned off where necessary. 

```html
<input type="tel" value="123-456-7890" name="phone" autocomplete="off" />
```



#### How does the `autocapitalize` attribute work?

Turn autocapitalization on and off for either the first letter of `word` ,`sentences` or `characters`. `autocapitalize` is a non-standard feature and W3C validator will complain about it, but some mobile browsers support it such as IOS safari and google chrome (desktops are not affected). 

By default `autocapitalize` is set to `sentences` but you must set it to `none` when you don't want to capitalize input. 

```html
<input type="text" name="full-name" autocapitalize="words" />
```



#### What is the `autocorrect` attribute?

Turn automatic spelling `on` and `off`. Although `autocorrect` is a non-standard feature and W3C will complain about it, Some browsers support it such as IOS mobile safari. 

It should however be turned off for names, addresses and other information where auto correction would be unhelpful. 

```html
<input type="text" name="full-name" autocorrect="off" />
```