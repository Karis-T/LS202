## Classes, IDs and Names

HTML gives us 3 ways to identify elements: by class, by id and by name. Class and id can be used by all elements whereas name can be used by some. `<input>` can use all 3:

```html
<input name="save" id="save-button" class="default-button" />
```

### What is the purpose of a Class attribute?

`class` attributes identify a set of elements you wish to give a consistent style to. We use the class attribute for:

- assigning one or more classes to an element using a space 
  eg. `class="executive management full-time"` 
- having many elements assigned to one class
- giving an element a semantic name to provide meaning rather than appearance
  eg. `teaching-assistant` vs `yellow-background`)
- applying CSS styles using class selectors  `.classname`  to select elements by class - `.teaching-assistant`
- adding more weighted specificity than just a type or tag name selector (though not as much as an id) `teaching-assistant` selector overrides the `tr` selector.

```html
<table>
  <tbody>
    <tr class="teaching-assistant">
      <td>Elizabeth</td>
      <td>JS230</td>
    </tr>
    <tr>
      <td>Kim</td>
      <td>LS202</td>
    </tr>
  </tbody>
</table>
```

```css
tr {
  background-color: grey;
  font-size: 200%;
}

.teaching-assistant {
  background-color: pink;
}
```

<table>
  <tbody style="color: black">
    <tr style="background-color: pink">
      <td>Elizabeth</td>
      <td>JS230</td>
    </tr>
    <tr style="background-color: grey">
      <td>Kim</td>
      <td>LS202</td>
    </tr>
  </tbody>
</table>

### What is the purpose of an ID attribute?

`id` attributes identify a single element you want to give a unique style to. Don't repeat the id anywhere else on the page as they are strictly meant to be used only once. We use the ID attribute to:

- give a unique id to an element
- assign only one id to an element (or none at all)
- give an element a semantic name. eg. `headline` vs. `big-font`
- use css id selectors `#idname` to select elements by their ID `#headline`
- ID selectors have the highest weighted specificity and outrank class and name tags no matter where they are placed in the cascade.
- use ID's sparingly

<p style="border: 1px solid grey; padding: 3% 4% 3% 4%;">Note that browsers don't tell you if you've used the same id on more than one element. Javascript doesn't like this so make sure you validate your code using W3C HTML validator.</p>

```html
<h4>This is a plain h4 heading</h4>
<h4 id="headline">This is my headline</h4>
```

```css
#headline {
  color: seagreen;
  font-size: 36px;
}
```

<h4>This is a plain h4 heading</h4>
<h4 style="color: seagreen; font-size: 36px;">This is my headline</h4>

### What is the purpose of a Name attribute?

`name` attributes bind form elements to data on a server. It doesn't play a role in styling and you shouldn't use it for that purpose. Use `class` or `id` attributes instead.

When you submit a form online, your browser will send form data or a query string as key value pairs; where the value of a `name` attribute becomes the `key` and what the user types in becomes the `value`.

```html
<form method="get" action="#">
	<label for="first-name-field">Your First Name:</label>
  <input type="text" name="first-name" id="first-name-field" />
  
  <label for="last-name-field">Your Last Name:</label>
	<input type="text" name="last-name" id="last-name-field" />
</form>
```

query string sent to server so the server can obtain the value:

```
first-name=Joe&last-name=Jones
```

id attributes are *not* sent to the server but id and name are used together in form elements. Use the same value for both id and name.

- not all elements use the name attribute. The one we're referring to here applies to input in forms. Other elements use a name attribute but it has a different meaning.
- always use a name attribute on form elements
- each name in a form should be unique to that form except for radio buttons / check boxes which belong to a group
- keep name values descriptive of the input that goes in there 
  eg. `name="last-name"` instead of a semantic one like `name="input-field"`



### How does the target attribute work?

`target="_blank"` is an attribute that belongs within the anchor element along side the `href=` attribute. It tells the browser to open the link in a new window or separate tab. 

some developers think that target blank is a bit presumptuous 