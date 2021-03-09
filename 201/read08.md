# Layout
## Key Concepts in Positioning Elements
### Building Blocks
CSS treats each HTML element as if it is in its
own box. This box will either be a block-level
box or an inline box.

* Block-level elements : start on a new line
* Inline elements : flow in between surrounding text

![1](https://www7.0zz0.com/2021/03/08/21/543121972.png)


### Containing Elements
If one block-level element sits inside another
block-level element then the outer box is
known as the containing or parent element.

![2](https://www8.0zz0.com/2021/03/08/21/152105705.png)

## Controlling the Position of Elements
CSS has the following positioning schemes that allow you to control
the layout of a page: normal flow, relative positioning, and absolute
positioning. You specify the positioning scheme using the position
property in CSS. You can also float elements using the float property

* Normal flow

Every block-level element
appears on a new line, causing
each item to appear lower down
the page than the previous one.
Even if you specify the width
of the boxes and there is space
for two elements to sit side-byside, they will not appear next
to each other. This is the default
behavior

* Relative Positioning

This moves an element from the
position it would be in normal
flow, shifting it to the top, right,
bottom, or left of where it
would have been placed. This
does not affect the position of
surrounding elements; they stay
in the position they would be in
in normal flow. (unless you tell the
browser to do something else)

* Absolute positioning

This positions the element
in relation to its containing
element. It is taken out of
normal flow, meaning that it
does not affect the position
of any surrounding elements
(as they simply ignore the
space it would have taken up).
Absolutely positioned elements
move as users scroll up and
down the page.

To indicate where a box should be positioned, you may also need to use
box offset properties to tell the browser how far from the top or bottom
and left or right it should be placed.

* Fixed Positioning

This is a form of absolute
positioning that positions
the element in relation to the
browser window, as opposed
to the containing element.
Elements with fixed positioning
do not affect the position of
surrounding elements and they
do not move when the user
scrolls up or down the page.

* Floating Elements

Floating an element allows
you to take that element out
of normal flow and position
it to the far left or right of a
containing box. The floated
element becomes a block-level
element around which other
content can flow.

## Normal Flow (position:static)

![3](https://www9.0zz0.com/2021/03/08/21/102673918.png)

## Relative Positioning (position:relative)

![4](https://www9.0zz0.com/2021/03/08/21/620953368.png)

## Absolute Positioning (position:absolute)

![5](https://www9.0zz0.com/2021/03/08/21/740876620.png)

## Fixed Positioning (position:fixed)

![6](https://www9.0zz0.com/2021/03/08/21/685108988.png)

##  Overlapping Elements (z-index)

![7](https://www9.0zz0.com/2021/03/08/22/760703506.png)

## Floating Elements (float)

![8](https://www9.0zz0.com/2021/03/08/22/750934308.png)

## Clearing Floats
The clear property allows you
to say that no element (within
the same containing element)
should touch the left or righthand sides of a box. It can take
the following values:

1. left : The left-hand side of the box
should not touch any other
elements appearing in the same
containing element.

2. right : The right-hand side of the
box will not touch elements
appearing in the same containing
element.

3. both : The right-hand side of the
box will not touch elements
appearing in the same containing
element.

4. none : Elements can touch either side

![9](https://www12.0zz0.com/2021/03/08/22/390205062.png)

## Creating Multi-Column Layouts with Floats

1. width : This sets the width of the
columns.
2. float : This positions the columns next
to each other.
3. margin : This creates a gap between the
columns.



