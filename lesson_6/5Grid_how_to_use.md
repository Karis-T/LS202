## What is Grid?

`grid` is a 2 dimensional grid-based layout system that changes the way we design grid based user interfaces. While css is used to layout our webpages, its never done a good job of it. tables, floats, positioning, and inline-block are all hacks and leave out a lot of important functioning (vertical centering). 

While flexbox has helped, its intended for simple 1 dimensional layouts, and not complex 2 dimensional ones. (flexbox and grid work well together).

Grid is the very first css module designed to solve website layout problems. 

### Grid Terminology:

1. Grid container

   - An element containing a grid
   - This is defined by setting: `display: grid`

   ```html
   <div class="site"> <!-- site would be a container for grid
   	entire site goes here -->  
   </div>   
   ```

2. Grid item

   - any direct (ist level) descendant of a grid container

   ```html
   <div class="site">
   	<header></header> <!--- grid item --->
   	<main></main><!--- grid item --->
   	<footer></footer><!--- grid item --->
   </div> 
   ```

3. Grid line

   - Any of the lines drawn inside the grid horizontal or vertical
   - these lines separate the gird into sections
   - grid lines are referenced by number. The start and end with the outer borders of the grid

![image-20210415125959768](C:\Users\Karis\AppData\Roaming\Typora\typora-user-images\image-20210415125959768.png)

4. Grid cell
   - any cell inside the grid (similar to a table cell)

![image-20210415130123727](C:\Users\Karis\AppData\Roaming\Typora\typora-user-images\image-20210415130123727.png)

5. Grid track

- vertical or horizontal rows or columns

![image-20210415130446849](C:\Users\Karis\AppData\Roaming\Typora\typora-user-images\image-20210415130446849.png)

6. Grid area

- defined rectangle inside the grid that covers more than 1 cell

![image-20210415130318480](C:\Users\Karis\AppData\Roaming\Typora\typora-user-images\image-20210415130318480.png)

7. Grid gap

- empty space between grid tracks (aka gutters)

![image-20210415130623413](C:\Users\Karis\AppData\Roaming\Typora\typora-user-images\image-20210415130623413.png)

### How to CSS Grid

1. Define a grid:

   ```html
   <div class="site">
     <header class="masthead"></header>
     <h1 class="page-title"></h1>
     <main class="main-content"></main>
     <aside class="sidebar"></aside>
     <footer class="footer"></footer>
   </div>
   ```

   ```css
   .site {
     display: grid;
     grid-template-columns: 2fr 1fr 1fr;
     grid-template-rows: auto 1fr 3fr;
   }
   ```

   - draw grid lines using:

     - `grid-template-columns` or `grid-template-rows` property

     - and a list of length values:  `em` `px` `%` `fr` etc (`fr` is new to grid)

     - grid items automatically populate from top left to bottom right based on HTML source order: ![image-20210415132103088](C:\Users\Karis\AppData\Roaming\Typora\typora-user-images\image-20210415132103088.png)

     - apply fractions to grid items each individual element

       ```css
       .masthead {  
       	grid-column: 2/4;
         grid-row: 2/3;
       }
       
       .page-title {
         grid-column: 1/4;
         grid-row: 1/2;
       }
       
       .main-content {
         grid-column: 1/2;
         grid-row: 2/4;
       }
       ```

       - `grid-template-areas` are applied to a grid container. it uses a text based grid map to apply grid area names to individual cells

       ![image-20210415132803200](C:\Users\Karis\AppData\Roaming\Typora\typora-user-images\image-20210415132803200.png)

       - `grid-template-areas` are applied to a grid container. it uses a text based grid map to apply grid area names to individual cells![image-20210415133040799](C:\Users\Karis\AppData\Roaming\Typora\typora-user-images\image-20210415133040799.png)

         ```css
         .site {
           display: grid;
           grid-template-columns: 2fr 1fr 1fr;
           grid-template-rows: auto 1fr 3fr;
           grid-template-areas:
             "title title title"
             "main header header"
             "main sidebar footer";
         }
         ```

         ```css
         .masthead {
           grid-area: header;
         }
         
         .page-title {
           grid-area: title;
         }
         
         .main-content {
           grid-area: main;
         }
         ```

         the above specifies what grid area the elements are placed in

         ![image-20210415133546871](C:\Users\Karis\AppData\Roaming\Typora\typora-user-images\image-20210415133546871.png)

         doing this makes responsive code so easy and simple as you just rearrange the grid template areas per media query and they will move around very easily 

### nested grids

- grids are not inherited by child elements - we have to create nested grids (for sub grids.)

### CSS grid practical approach for today

1. Build accessible mobile first layout without grid
2. use mobile first layout as fallback for all browsers
3. use @support to detect `grid` support on browsers
4. at appropriate breakpoints, create a layout with grid and grid-areas
5. explore new layouts as viewports widen
6. firefox has a grid inspector!
7. Rachel Andrews website is doctrine for grid
8. mdn has exhaustive info
9. css tricks too