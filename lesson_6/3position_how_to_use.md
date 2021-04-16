## What is positioning?

### How do I offset properties?

This is done with the properties:

- `top`
- `right`
- `bottom`
- `left`

These properties work in conjunction with `position` to determine:

- how far you want to move an element
- what direction you want to move an element

offsets measure the *inward* distance from the side of the container. eg. a 
`bottom: 50px` displays a position shifted down 50px from the top of the container. 
(ie. it doesn't include the size of the container when shifting positions)

negative offsets shift elements in the opposite direction.

negative margins have the ability to center positioned elements

### How does the `position` property work?

This property tells the browser how to position selected elements

#### What is `position: static` ?

Static is the default element position. 

- `floated`,` grid`, `flex`, `absolute` and `fixed` positioning all are removed from the document flow
- `static` and `relative` are apart of the page flow and don't get removed.
- offset properties don't affect static elements

#### What is `position: relative`?

moves an element to a new position relative to where the browser would put it normally. When using relative positioning:

- give at most 1 vertical offset
- and at most 1 horizontal offset
- css standards allow you to use all offsets at the same time is
  - `left` overrides `right` for left-to-right languages. (english)
  - `right` overrides `left` for right-to-left languages. (arabic)
  - `top` overrides `bottom` at all times.

- **relative positioning does not remove an item from the document flow** . This means the browser stacks the next element as if the current element wasn't moved from its original position. 

  ![Relative positioning, right](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_6/positioning-03.png)

  ```css
  .pos {
    display: relative;
    right: 60px;
  }
  
  .neg {
    display: relative;
    right: -60px;
  }
  ```

- neighboring elements respect the area of the previous elements absent of positioning offsets and does not push them around

  ![Relative positioning, left](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_6/positioning-04.png)

  ```css
  .pos {
    display: relative;
    left: 50px;
  }
  
  .neg {
    display: relative;
    left: -50px;
  }
  ```

#### What is `position: absolute`?

makes the browser move the element to a new position *inside* a container. by default, the container is the **nearest ancestor that has a `position` of:**

- relative
- absolute
- sticky (not discussed)

if neither is present the browser uses the initial containing block (`body`) - ie. the browser positions the element at an absolute position on the page.

![Absolute positioning](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_6/positioning-05.png)

- to center a box inside a container set all 4 offset properties to the same value (will not work if an element has a set height / width)

  ```css
  .absolute-1 {
    background-color: lightgreen;
    bottom: 33%;
    left: 33%;
    position: absolute;
    right: 33%;
    top: 33%;
  }
  ```

- to push a box into a corner inside a container use opposing 2 positions to do so: eg. if you want to push a box to the top left hand corner of the page use the `bottom` and `right` positioning.

  ```css
  .absolute-2 {
    background-color: cyan;
    bottom: 150px;
    left: 0;
    position: absolute;
    right: 20px;
    top: 0;
  }
  ```

- negative offsets move a box outside of its container:

  ```css
  .absolute-3 {
    background-color: pink;
    bottom: -50px;
    left: 100px;
    position: absolute;
    right: -40px;
    top: 150px;
  }
  ```

Note: **Absolute positioning** removes elements from normal doc flow meaning the browser won't treat that space as occupies:

![Absolute positioning and the flow](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_6/positioning-06.png)

The black box is `static` and doesn't see any other element present and remains in the same position

#### What is `position: fixed`?

sets an element to a fixed position in a browser's window, which means It will not move if the user scrolls the page. eg. Sticky navigation at the top of a website.

```css
header {
  background-color: lightgreen;
  font-size: 4rem;
  height: 8rem;
  left: 0;
  line-height: 8rem;
  opacity: .75;
  position: fixed;
  text-align: center;
  top: 0;
  width: 100%;
}
```

![Fixed positioning](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_6/positioning-07.png)