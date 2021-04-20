# Grid 

## Properties for the Parent (Grid Container)

### display
Defines the element as a grid container and establishes a new grid formatting context for its contents.

Values:
* grid – generates a block-level grid
* inline-grid – generates an inline-level grid

`.container {
  display: grid | inline-grid;
} `

### grid-template-columns
### grid-template-rows
Defines the columns and rows of the grid with a space-separated list of values. The values represent the track size, and the space between them represents the grid line.

Values:

* < track-size> – can be a length, a percentage, or a fraction of the free space in the grid (using the fr unit)
* < line-name> – an arbitrary name of your choosing

Examples:

When you leave an empty space between the track values, the grid lines are automatically assigned positive and negative numbers:

` .container {
  grid-template-columns: 40px 50px auto 50px 40px;
  grid-template-rows: 25% 100px auto;
}
`

![1](https://css-tricks.com/wp-content/uploads/2018/11/template-columns-rows-01.svg)

But you can choose to explicitly name the lines. Note the bracket syntax for the line names:

>.container {
  grid-template-columns: [first] 40px [line2] 50px [line3] auto [col4-start] 50px [five] 40px [end];
  grid-template-rows: [row1-start] 25% [row1-end] 100px [third-line] auto [last-line];
}

![2](https://css-tricks.com/wp-content/uploads/2018/11/template-column-rows-02.svg)

### grid-template-areas
Defines a grid template by referencing the names of the grid areas which are specified with the grid-area property. Repeating the name of a grid area causes the content to span those cells. A period signifies an empty cell. The syntax itself provides a visualization of the structure of the grid.

Values:

* < grid-area-name> – the name of a grid area specified with grid-area
* . – a period signifies an empty grid cell
* none – no grid areas are defined

Example:

` .item-a {
  grid-area: header;
}
.item-b {
  grid-area: main;
}
.item-c {
  grid-area: sidebar;
}
.item-d {
  grid-area: footer;
}
.container {
  display: grid;
  grid-template-columns: 50px 50px 50px 50px;
  grid-template-rows: auto;
  grid-template-areas: 
    "header header header header"
    "main main . sidebar"
    "footer footer footer footer";
}`

![3](https://css-tricks.com/wp-content/uploads/2018/11/dddgrid-template-areas.svg)

### grid-template
A shorthand for setting grid-template-rows, grid-template-columns, and grid-template-areas in a single declaration

Values:
* none – sets all three properties to their initial values
* < grid-template-rows> / < grid-template-columns> – sets grid-template-columns and grid-template-rows to the specified values, respectively, and sets grid-template-areas to none

`.container {
  grid-template: none | <grid-template-rows> / <grid-template-columns>;
}`

### column-gap row-gap grid-column-gap grid-row-gap
Specifies the size of the grid lines. You can think of it like setting the width of the gutters between the columns/rows.

Example:

`.container {
  grid-template-columns: 100px 50px 100px;
  grid-template-rows: 80px auto 80px; 
  column-gap: 10px;
  row-gap: 15px;
}`

![4](https://css-tricks.com/wp-content/uploads/2018/11/dddgrid-gap.svg)

### gap grid-gap

Specifies the size of the grid lines. You can think of it like setting the width of the gutters between the columns/rows.

Example:

`.container {
  grid-template-columns: 100px 50px 100px;
  grid-template-rows: 80px auto 80px; 
  column-gap: 10px;
  row-gap: 15px;
}`

![5](https://css-tricks.com/wp-content/uploads/2018/11/dddgrid-gap.svg)

## Properties for the Children (Grid Items)

### grid-column-start grid-column-end grid-row-start grid-row-end

Determines a grid item’s location within the grid by referring to specific grid lines. grid-column-start/grid-row-start is the line where the item begins, and grid-column-end/grid-row-end is the line where the item ends.

Values:

* < line> – can be a number to refer to a numbered grid line, or a name to refer to a named grid line
* span < number> - the item will span across the provided number of grid tracks
* span < name> – the item will span across until it hits the next line with the provided name
* auto – indicates auto-placement, an automatic span, or a default span of one

Examples:

`.item-a {
  grid-column-start: 2;
  grid-column-end: five;
  grid-row-start: row1-start;
  grid-row-end: 3;
}`

![6](https://css-tricks.com/wp-content/uploads/2018/11/grid-column-row-start-end-01.svg)

`.item-b {
  grid-column-start: 1;
  grid-column-end: span col4-start;
  grid-row-start: 2;
  grid-row-end: span 2;
}`

![7](https://css-tricks.com/wp-content/uploads/2018/11/grid-column-row-start-end-02.svg)


### grid-column grid-row

Shorthand for grid-column-start + grid-column-end, and grid-row-start + grid-row-end, respectively.

Example:

`.item-c {
  grid-column: 3 / span 2;
  grid-row: third-line / 4;
}`

![8](https://css-tricks.com/wp-content/uploads/2018/11/grid-column-row.svg)

### grid-area

Gives an item a name so that it can be referenced by a template created with the grid-template-areas property. Alternatively, this property can be used as an even shorter shorthand for grid-row-start + grid-column-start + grid-row-end + grid-column-end.

Values:

* < name> – a name of your choosing
* < row-start> / < column-start> / < row-end> / < column-end> – can be numbers or named lines

Examples: 

`.item-d {
  grid-area: header;
}`

![9](https://css-tricks.com/wp-content/uploads/2018/11/grid-area.svg)

# References

> https://css-tricks.com/snippets/css/complete-guide-grid/


