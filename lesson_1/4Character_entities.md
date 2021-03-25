## Character Entities

Browsers don't display tags; instead it interprets them as instructions for rendering the page.

by default browsers compress all whitespace to a single space character, and all paragraphs breaks are lost.

Browsers don't know what to do with preformatted text such as <p>. Since this is a paragraph tag the browser tries to interpret is and begins a new paragraph. This can lead to unexpected formatting.

To resolve this `>` `<` and other reserved characters must be replaced with character entities.

### What are HTML character entities?

There are many entities for reserved or special characters available but most developers will only use about a dozen and look them up when needed. Entities replace literal `<` and `>` so the browser doesn't interpret them as code. 

```
<p> becomes &lt;p&gt;
```

Ampersand is another potential character entity if it is used without whitespace next to either side of it. As a rule developers replace it anyways:

```
& becomes &amp;
```

And double quotes:

```
"Hello, World" becomes &quot;Hello, World;&quot
```

All entities follow the pattern of an `&` prefixing and a `;`  as a suffix. in-between is usually one or more alphanumeric characters. Try to use letters over numbers though

eg. `&` can also be represented as `&#38;` but the preferred is `&amp;` .

<p style="border: 1px solid grey; padding: 3% 4% 3% 4%;">Note: browsers or validators don't complain if you use < > or & bare. You may only find out if it starts causing problems on your page. Try to be vigilant about entities.</p>