## Software

### What are HTML / CSS validators and when should I use them?

- Validators focus on conforming to standards, detecting errors, elements no longer in use, poor use of element nesting and non-standard attributes and properties.
- for this course copy and paste your code into the [W3C HTML Validator](https://validator.w3.org/#validate_by_input) . Try to Validate regularly as It helps catch issues before it develops into a bug. You should validate when:
  - After first draft of HTML
  - After significant changes to HTML
  - Page rendering problems
  - before a HTML code review
  - before deploying HTML
- Use the [W3c CSS Validator](https://jigsaw.w3.org/css-validator/#validate_by_input). Check your CSS when you check your HTML and if you've made big changes to your CSS.
- Checking can be a pain and a hard habit to form but validating regularly can help prevent a lot of grief later down the line. 

>The W3C plugin for Atom ignores the CSS validator's warning level that you set in your preferences and checks for a variety of minor conditions that you can typically ignore. Fix the items identified as errors, but feel free to skip those marked as warnings unless you see unexpected styling behavior. You can also use the web-based version of the W3C Validator for CSS.

### What are Linters?

- Linters look for errors and style issues in your code. 
- Linters pick on the style and use of code and aim for best practices and code conventions rather than standards 
- An example is looking at code indentation and formatting
- There are many linters for different languages, including HTML and CSS.