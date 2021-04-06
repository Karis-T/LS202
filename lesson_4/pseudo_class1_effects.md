### Pseudo Classes

<style>
  nav ul {
   list-style: none;
   padding-left: 0;
   width: 100%;
  }
  nav li {
   width: 25%;
   text-align: center;
   display: inline-block;
  }
   nav a {
   box-sizing: border-box;
   display: inline-block;
   line-height: 2.5;
   padding: 0 10px;
   text-decoration: none;
   width: 100%;
  }
  nav a:hover,  nav a:focus {
   background-color: blue;
   color: white;
  }
</style>
<nav>
  <ul>
    <li><a href="#">Home</a></li><li><a href="#">Projects</a></li><li><a href="#">Team</a></li><li><a href="#">Help</a></li>
  </ul>
</nav>

Navigation menus can use pseudo-classes to highlight each tab when you hover over it using `:hover` and `:focus`

- `:hover` will alter the properties when your mouse is hovering over a selected element

- `:focus` will alter the properties when you have clicked, tabbed or indicated some other form of focus on the selected element
- `:lastchild` selects the last child/nested element of a parent/container
- `:full-screen` detects the browsers screen size

There are over 30 pseudo classes in CSS which are keywords that style the state of the selected elements. eg. `:hover` state for a link. 

This is not to be confused with `pseudo elements` which are used to style a specific part of a selected element eg. `p::first-line` styles the first line of every paragraph.

```css
nav a:hover,  nav a:focus {
  background-color: blue;
  color: white;
}
```



