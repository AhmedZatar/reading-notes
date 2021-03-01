# Lists
There are lots of occasions when we
need to use lists. HTML provides us with
three different types:

* **Ordered lists** are lists where each item in the list is
numbered. For example, the list might be a set of steps for
a recipe that must be performed in order, or a legal contract
where each point needs to be identified by a section
number.

* **Unordered lists** are lists that begin with a bullet point
(rather than characters that indicate order)

* **Definition lists** are made up of a set of terms along with the
definitions for each of those terms.

## Ordered Lists
The ordered list is created with
the < ol > element.

Each item in the list is placed
between an opening < li > tag
and a closing < /li > tag. 

![1](https://www4.0zz0.com/2021/03/01/18/785105808.png)

## Unordered Lists
The unordered list is created
with the < ul > element.

Each item in the list is placed
between an opening < li > tag
and a closing < /li > tag.

![2](https://www2.0zz0.com/2021/03/01/18/832290789.png)

## Definition Lists
The definition list is created with
the < dl > element and usually
consists of a series of terms and
their definitions.
Inside the < dl > element you will
usually see pairs of < dt > and
< dd > elements.

![3](https://www6.0zz0.com/2021/03/01/19/803010668.png)

# Boxes
## Box Dimensions
By default a box is sized just big
enough to hold its contents. To
set your own dimensions for a
box you can use the height and
width properties.

The most popular ways to
specify the size of a box are
to use pixels, percentages, or
ems. Traditionally, pixels have
been the most popular method
because they allow designers to
accurately control their size.

![4](https://www10.0zz0.com/2021/03/01/19/691774591.png)

## Border, Margin & Padding
1. Border

Every box has a border (even if
it is not visible or is specified to
be 0 pixels wide). The border
separates the edge of one box
from another.

2. Margin

Margins sit outside the edge
of the border. You can set the
width of a margin to create a
gap between the borders of two
adjacent boxes.

3. Padding

Padding is the space between
the border of a box and any
content contained within it.
Adding padding can increase the
readability of its contents.

## Border Width
The border-width property
is used to control the width
of a border. The value of this
property can either be given
in pixels or using one of the
following values:
(thin, medium, thick)

## Border Style
You can control the style of a
border using the border-style
property. This property can take
the following values :

![5](https://www11.0zz0.com/2021/03/01/19/675639762.png)

## Margin
The margin property controls
the gap between boxes. Its value
is commonly given in pixels,
although you may also use
percentages or ems.

If one box sits on top of another,
margins are collapsed , which
means the larger of the two
margins will be used and the
smaller will be disregarded.

![6](https://www9.0zz0.com/2021/03/01/19/608500507.png)

# ARRAYS
An array is a special type of variable. It doesn't
just store one value; it stores a list of values

Arrays are especially helpful
when you do not know how
many items a list will contain
because, when you create the
array, you do not need to specify
how many values it will hold.

## CREATING AN ARRAY
You create an array and give it
a name just like you would any
other variable (using the var
keyword followed by the name of
the array).

The values are assigned to the
array inside a pair of square
brackets, and each value is
separated by a comma. The
values in the array do not need
to be the same data type, so you
can store a string, a number and
a Boolean all in the same array.

![8](https://www7.0zz0.com/2021/03/01/00/356121922.png)

# JavaScript if else and else if
Very often when you write code, you want to perform different actions for different decisions.

You can use conditional statements in your code to do this.

In JavaScript we have the following conditional statements:

* Use if to specify a block of code to be executed, if a specified condition is true

* Use else to specify a block of code to be executed, if the same condition is false

* Use else if to specify a new condition to test, if the first condition is false

* Use switch to specify many alternative blocks of code to be executed

# TRUTHY & FALSY VALUES
Falsy values are treated as if they
are fa 1 se. The table to the left
shows a hi ghScore variable with
a series of values, all of which
are falsy. 

Falsy values can also be treated
as the number 0 . 

Truthy values are treated as if
they are true. Almost everything
that is not in the falsy table can
be treated as if it were true. 

Truthy values can also be treated
as the number 1. 

# JavaScript Loops
JavaScript supports different kinds of loops:
* for - loops through a block of code a number of times
* for/in - loops through the properties of an object
* for/of - loops through the values of an iterable object
* while - loops through a block of code while a specified condition is true
* do/while - also loops through a block of code while a specified condition is true

## The For Loop
The for loop has the following syntax:

![9](https://www2.0zz0.com/2021/03/01/20/481131109.png)

Statement 1 is executed (one time) before the execution of the code block.

Statement 2 defines the condition for executing the code block.

Statement 3 is executed (every time) after the code block has been executed.

### Example

![10](https://www2.0zz0.com/2021/03/01/20/349768761.png)

From the example above, you can read:

Statement 1 sets a variable before the loop starts (var i = 0).

Statement 2 defines the condition for the loop to run (i must be less than 5).

Statement 3 increases a value (i++) each time the code block in the loop has been executed.

## The While Loop

The while loop loops through a block of code as long as a specified condition is true.

### Example
In the following example, the code in the loop will run, over and over again, as long as a variable (i) is less than 10:

![11](https://www12.0zz0.com/2021/03/01/20/260018552.png)

## The Do/While Loop
The do/while loop is a variant of the while loop. This loop will execute the code block once, before checking if the condition is true, then it will repeat the loop as long as the condition is true.

### Example
The example below uses a do/while loop. The loop will always be executed at least once, even if the condition is false, because the code block is executed before the condition is tested:

![12](https://www5.0zz0.com/2021/03/01/20/461939321.png)


## References
> JAVASCRIPT & JQUERY
Interactive Front-End Web Development
JON DUCKETT

> from https://www.w3schools.com/
