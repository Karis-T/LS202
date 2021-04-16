## What is Responsive Design?

Responsive design is about writing css that changes with different output devices (or screen sizes). As the website must be functional whether on a mobile phone or a computer screen 

### What are media Queries?

They define the styles that change based on the browser size. This lets us customize looks anything from mobile devices to large desktop displays.

```css
a {
  color: #f00;
}

@media (max-width: 480px) {
  a {
    color: #06c;
  }
}
```

```css
@media screen and (max-width: 1600px) {
  /* CSS for 1600px (or smaller) screens (no printers!) */
}
```

The media query above changes the link color on smaller devices (mobile phones are typically 480px wide or smaller)

- You can use logical operators `not` `and` `only` and `,` comma
- You can choose different media types like `all` `screen` `print` or `speech` 
- `min-width` `max width` and `screen` is the most commonly used terms

#### What is the difference between mobile first vs desktop first? 

You must decide if you want your website to primarily viewed on desktop or mobile. ie - the device expected when no media query is active

- most developers use the "mobile first" approach as best practice. Media queries are then used to handle larger devices. This usually results in faster downloads on mobile devices
- colors typically don't change between devices so its common to keep all the colors at the top of the page

```css
/* CSS for all cell phones and shared cross-browser CSS */

@media screen and (min-width: 481px) {
  /* CSS for tablets and larger */
}

@media screen and (min-width: 961px) {
  /* CSS for small desktop and laptop screens and larger */
}

@media screen and (min-width: 1501px) {
  /* CSS for large laptop and desktop displays */
}

@media print {
  /* CSS for printers */
}
```

#### What are breakpoints?

Are the variety of browser/screen sizes for media queries. Since all mobile devices and desktops come in a variety of sizes It's more appropriate to ask what layout is best over a range of screen sizes- And then build a media query from it.

#### How do you Emulate Devices in Google Chrome?

If you don't own a popular device you can view it from google chromes inspector:

1. Open the inspector.
2. Click the emulation icon in the top bar (it looks like a smartphone resting atop a tablet in Chrome v64 - other versions may differ).
3. Several drop-downs will appear above the web page.
4. Select iPhone 8 from the "Responsive" drop-down.
5. Refresh the page to ensure the page loads everything it needs.

You can also test performance by choosing the mid or low-tier mobile device and see what it looks like with a slower connection. You can also edit the list of devices too.

#### How do you use your page on multiple devices?

you must use the following `meta` element in the `head` part of your HTML if you're designing your app for responsive devices:

```html
<meta name="viewport" content="width=device-width, initial-scale=1" />
```

It tells mobile devices how to handle the page and without it they may display miniature versions of the page instead of your media query for mobile devices. [Don't use this](http://blog.javierusobiaga.com/stop-using-the-viewport-tag-until-you-know-ho) element if your website is not designed to be responsive.