## Build Tables in HTML

### What Are the Various Table Tags?

- `<table>` creates a *table*
- `<tr>` creates one *table row*. Each row has zero or more cells
- `<td>` creates one cell for *table data*
- `<th>` creates one *table heading.* The first cell in a row / column is usually the heading, but this tag is optional. The browser renders table headings different to table data
- use the `rowspan` attribute to have a cell or heading span multiple rows
- use the `colspan` attribute to have a cell or heading span multiple columns
- use `border-collapse: collapse` property to remove space between borders in a table 

a simple table without semantics:

```html
<table>
  <tr>                      <!-- row 1 -->
    <th>Color Name</th>       <!-- column header 1 -->
    <th>Color Hex</th>        <!-- column header 2 -->
    <th>Color Decimal</th>    <!-- column header 3 -->
  </tr>

  <tr>                      <!-- row 2 -->
    <th>red</th>              <!-- row header (column 1) -->
    <td>#f00</td>             <!-- data cell 1 (column 2) -->
    <td>255, 0, 0</td>        <!-- data cell 2 (column 3) -->
  </tr>

  <tr>                      <!-- row 3 -->
    <th>green</th>            <!-- row header (column 1) -->
    <td>#0f0</td>             <!-- data cell 1 (column 2) -->
    <td>0, 255, 0</td>        <!-- data cell 2 (column 3) -->
  </tr>

  <tr>                      <!-- row 4 -->
    <th>blue</th>             <!-- row header (column 1) -->
    <td>#00f</td>             <!-- data cell 1 (column 2) -->
    <td>0, 0, 255</td>        <!-- data cell 2 (column 3) -->
  </tr>
</table>
```

<table>
  <tr>                      <!-- row 1 -->
    <th>Color Name</th>       <!-- column header 1 -->
    <th>Color Hex</th>        <!-- column header 2 -->
    <th>Color Decimal</th>    <!-- column header 3 -->
  </tr><tr>                      <!-- row 2 -->
    <th>red</th>              <!-- row header (column 1) -->
    <td>#f00</td>             <!-- data cell 1 (column 2) -->
    <td>255, 0, 0</td>        <!-- data cell 2 (column 3) -->
  </tr>
<tr>                      <!-- row 3 -->
    <th>green</th>            <!-- row header (column 1) -->
    <td>#0f0</td>             <!-- data cell 1 (column 2) -->
    <td>0, 255, 0</td>        <!-- data cell 2 (column 3) -->
  </tr>
<tr>                      <!-- row 4 -->
    <th>blue</th>             <!-- row header (column 1) -->
    <td>#00f</td>             <!-- data cell 1 (column 2) -->
    <td>0, 0, 255</td>        <!-- data cell 2 (column 3) -->
  </tr>
</table>
### What are the semantic Table elements and heading scope?

- `<thead>`, `<tbody>` and `<tfoot>` creates a header, body and footer within a table. These are used to give semantic meaning to table elements
- You can also use the `scope` attribute to identify the difference between `th` columns and `th` rows
- use  `:nth-child()` pseudo-class to select the first, second, and third rows of the `tbody`.
  - A variation of `:nth-child()` uses the `2n+2` as an argument to the parameter to select every other row.

```html
<table>
  <thead>                              <!-- heading rows -->
    <tr>                                 <!-- row 1 -->
      <th scope="col">Color Name</th>      <!-- column header 1 -->
      <th scope="col">Color Hex</th>       <!-- column header 2 -->
      <th scope="col">Color Decimal</th>   <!-- column header 3 -->
    </tr>
  </thead>

  <tbody>                              <!-- body rows -->
    <tr>                               <!-- row 2 -->
      <th scope="row">red</th>         <!-- row header (column 1) -->
      <td>#f00</td>                   <!-- data cell 1 (column 2) -->
      <td>255, 0, 0</td>               <!-- data cell 2 (column 3) -->
    </tr>

    <tr>                               <!-- row 3 -->
      <th scope="row">green</th>       <!-- row header (column 1) -->
      <td>#0f0</td>                   <!-- data cell 1 (column 2) -->
      <td>0, 255, 0</td>               <!-- data cell 2 (column 3) -->
    </tr>

    <tr>                                <!-- row 4 -->
      <th scope="row">blue</th>         <!-- row header (column 1) -->
      <td>#00f</td>                     <!-- data cell 1 (column 2) -->
      <td>0, 0, 255</td>                <!-- data cell 2 (column 3) -->
    </tr>
  </tbody>

  <tfoot>                            <!-- footer -->
    <tr>                              <!-- row 5 -->
      <td>name</td>                   <!-- data cell 1 (column 1) -->
      <td>#rrggbb</td>                <!-- data cell 2 (column 2) -->
      <td>red, green, blue</td>       <!-- data cell 3 (column 3) -->
    </tr>
  </tfoot>
</table>
```



```css
table {
  font-size: 1.5rem;
}
/* all table headers */
th {
  font-size: 1.75rem;
}
/* all table body rows*/
tbody tr {
  font-style: italic;
}
/* 1st table row */
tbody tr:nth-child(1) {
  color: red;
}
/* 2nd table row */
tbody tr:nth-child(2) {
  color: green;
}
/* 3rd table row */
tbody tr:nth-child(3) {
  color: blue;
}
/* table footer row */
tfoot tr {
  font-size: 1rem;
}
/* all table footer data */
tfoot td {
  border-top: 1px solid gray;
}
/* all table data */
td {
  text-align: center;
}
/* all heading columns */
[scope="col"] {
  padding: 0 10px;
  text-decoration: underline;
}
/* all heading rows */
[scope="row"] {
  text-transform: uppercase;
}
```

![Enhanced color table](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_4/tables-overview-02.png)