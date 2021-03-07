# Domain Modeling
Domain modeling is the process of creating a conceptual model in code for a specific problem. A model describes the various entities, their attributes and behaviors, as well as the constraints that govern the problem domain. An entity that stores data in properties and encapsulates behaviors in methods is commonly referred to as an object-oriented model.

A domain model that's articulated well can verify and validate the understanding of a specific problem among various stakeholders. As a communication tool, it defines a vocabulary that can be used within and between both technical and business teams.

# Tables
## What's a Table?
A table represents information in a grid format.
Examples of tables include financial reports, 

## Basic Table Structure

* < table >
The < table > element is used
to create a table. The contents
of the table are written out row
by row.

* < tr >
You indicate the start of each
row using the opening < tr > tag.
(The tr stands for table row.)
It is followed by one or more
< td > elements (one for each cell
in that row).
At the end of the row you use a
closing < /tr > tag.

* < td >
Each cell of a table is
represented using a < td >
element. (The td stands for
table data.)
At the end of each cell you use a
closing < /td > tag.

![1](https://www11.0zz0.com/2021/03/07/22/303775279.png)

## Table Headings
The < th > element is used just
like the < td > element but its
purpose is to represent the
heading for either a column or
a row. (The th stands for table
heading.)
Even if a cell has no content,
you should still use a < td > or
< th > element to represent
the presence of an empty cell
otherwise the table will not
render correctly.

![2](https://www9.0zz0.com/2021/03/07/22/377673853.png)

## Spanning ColumnS
Sometimes you may need the
entries in a table to stretch
across more than one column.
The colspan attribute can be
used on a < th > or < td > element
and indicates how many columns
that cell should run across.

![3](https://www7.0zz0.com/2021/03/07/22/813088629.png)

## Spanning Rows
You may also need entries in
a table to stretch down across
more than one row.
The rowspan attribute can be
used on a < th > or < td > element
to indicate how many rows a cell
should span down the table.

![4](https://www14.0zz0.com/2021/03/07/22/594283076.png)

## Long Tables
here are three elements that
help distinguish between the
main content of the table and
the first and last rows (which can
contain different content).
These elements help people
who use screen readers and also
allow you to style these sections
in a different manner than the
rest of the table 

1. < thead > :
The headings of the table should
sit inside the < thead > element.
2. < tbody > :
The body should sit inside the
< tbody > element.
3. < tfoot > :
The footer belongs inside the
< tfoot > element.

![5](https://www9.0zz0.com/2021/03/07/22/566711648.png)

![6](https://www9.0zz0.com/2021/03/07/22/237665873.png)

## Width & Spacing
There are some outdated
attributes which you should not
use on new websites. You may,
however, come across some
of them when looking at older
code, so I will mention them
here. All of these attributes have
been replaced by the use of CSS.
The width attribute was used
on the opening < table > tag to
indicate how wide that table
should be and on some opening
< th > and < td > tags to specify
the width of individual cells.
The value of this attribute is
the width of the table or cell in
pixels.

![7](https://www10.0zz0.com/2021/03/07/23/473217281.png)

## Border & Background
The border attribute was used
on both the < table > and < td >
elements to indicate the width of
the border in pixels.
The bgcolor attribute was used
to indicate background colors
of either the entire table or
individual table cells. The value
is usually a hex code

![8](https://www14.0zz0.com/2021/03/07/23/815240336.png)

# Object
## Updating an object
to update the value of properties, use dot natation or square brackts, they work on object created using literal or constructor notation to delete a property, use the delete keyword.

![9](https://www11.0zz0.com/2021/03/07/23/409603058.png)

## CREATING MANY OBJECTS CONSTRUCTOR NOTATION 
Sometimes you will want several objects to represent similar things.
Object constructors can use a function as a template for creating objects.
First, create the template with the object's properties and methods. 

## CREATING OBJECTS USING CONSTRUCTOR SYNTAX

![10](https://www7.0zz0.com/2021/03/07/23/154249625.png)

## CREATE & ACCESS OBJECTS CONSTRUCTOR NOTATION 

![11](https://www5.0zz0.com/2021/03/07/23/681399855.png)

## ADDING AND REMOVING PROPERTIES 

![12](https://www5.0zz0.com/2021/03/07/23/824114990.png)

## THIS (IT IS A KEYWORD) 
The keyword this is commonly used inside functions and objects.
Where the function is declared alters what this means. It always refers
to one object, usually the object in which the function operates. 

## RECAP: STORING DATA
In JavaScript, data is represented using name/value pairs.
To organize your data, you can use an array or object to group a set of
related values. In arrays and objects the name is also known as a key. 

## Arrays are objects 
Array are actually a spceial type of object. they hold a related set of key/value(like all object), but the key for each value is its index number.

![13](https://www7.0zz0.com/2021/03/07/23/424550396.png)

# THE DOCUMENT OBJECT 
The topmost object in the Document Object Model (or DOM) is the
document object. It represents the web page loaded into the current
browser window or tab.

![14](https://www4.0zz0.com/2021/03/07/23/101065664.png)

# DATA TYPES REVISITED
1. String (If a variable, or the property of an object,
contains a string, you can use the properties and
methods of the String object on it.)
2. Number ( If a variable, or property of an object,
stores a number, you can use the properties and
methods of the Number object on it)
3. Boolean (There is a Boo 1 ean object. It is rarely used.)
4. Undefined (a variable that has been declared, but
no value has been assigned to it yet)
5. Null (a variable with no value - it may have had
one at some point, but no longer has a value) 
6. Object (Under the hood, arrays and functions are considered
types of objects. )

# MATH OBJECT
The Math object has properties and methods
for mathematical constants and functions. 

![15](https://www6.0zz0.com/2021/03/07/23/729435667.png)

# References
> JAVASCRIPT & JQUERY
Interactive Front-End Web Development
JON DUCKETT

> HTML & CSS
Design and Build Websites
Jon Ducket

> from https://github.com/codefellows/domain_modeling#domain-modeling
