# Links
## Writing Links
Links are created using the < a > element. Users can click on anything
between the opening < a > tag and the closing < /a > tag. You specify
which page you want to link to using the href attribute.

![1](https://www14.0zz0.com/2021/03/02/20/845023471.png)

## Linking to Other Sites
Links are created using the < a>
element which has an attribute
called href. The value of the
href attribute is the page that
you want people to go to when
they click on the link.
Users can click on anything that
appears between the opening
< a> tag and the closing < /a>
tag and will be taken to the page
specified in the href attribute.
When you link to a different
website, the value of the href
attribute will be the full web
address for the site, which is
known as an absolute URL.

![2](https://www10.0zz0.com/2021/03/02/20/658862023.png)

## Linking to Other Pages on the Same Site
When you are linking to other
pages within the same site,
you do not need to specify the
domain name in the URL. You
can use a shorthand known as a
relative URL.
If all the pages of the site are in
the same folder, then the value
of the href attribute is just the
name of the file.

![3](https://www10.0zz0.com/2021/03/02/20/785198181.png)

## Email Links
To create a link that starts up
the user's email program and
addresses an email to a specified
email address, you use the < a >
element. However, this time the
value of the href attribute starts
with mailto: and is followed by
the email address you want the
email to be sent to

![4](https://www14.0zz0.com/2021/03/02/20/712580072.png)

## Opening Links in a New Window
If you want a link to open in a
new window, you can use the
target attribute on the opening
< a> tag. The value of this
attribute should be _blank.
One of the most common
reasons a web page author
might want a link to be opened
in a new window is if it points to
another website. In such cases,
they hope the user will return
to the window containing their
site after finishing looking at the
other one.

![5](https://www14.0zz0.com/2021/03/02/20/219234907.png)

# Layout

## Building Blocks
CSS treats each HTML element as if it is in its
own box. This box will either be a block-level
box or an inline box.

* Block-level elements

start on a new line
Examples include:
< h1> < p> < ul> < li>

* Inline elements
flow in between
surrounding text
Examples include:
< img > < b > < i >

## Containing Elements

If one block-level element sits inside another
block-level element then the outer box is
known as the containing or parent element.

It is common to group a number of elements together inside a < div>
(or other block-level) element. For example, you might group together
all of the elements that form the header of a site (such as the logo and
the main navigation). The < div> element that contains this group of
elements is then referred to as the containing element.

## Controlling the Position of Elements
CSS has the following positioning schemes that allow you to control
the layout of a page: normal flow, relative positioning, and absolute
positioning. You specify the positioning scheme using the position
property in CSS. You can also float elements using the float property

![6](https://www6.0zz0.com/2021/03/02/20/897778051.png)

## box offset
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
content can flow 

# FUNCTION
## WHAT IS A FUNCTION? 
Functions let you group a series of statements together to perform a
specific task. If different parts of a script repeat the same task, you can
reuse the function (rather than repeating the same set of statements). 

## JavaScript Function Syntax

A JavaScript function is defined with the function keyword, followed by a name, followed by parentheses ().

Function names can contain letters, digits, underscores, and dollar signs (same rules as variables).

The parentheses may include parameter names separated by commas:
(parameter1, parameter2, ...)

The code to be executed, by the function, is placed inside curly brackets: {}

Function parameters are listed inside the parentheses () in the function definition.

Function arguments are the values received by the function when it is invoked.

Inside the function, the arguments (the parameters) behave as local variables.

## Function Invocation
The code inside the function will execute when "something" invokes (calls) the function:

1. When an event occurs (when a user clicks a button)
2. When it is invoked (called) from JavaScript code
3. Automatically (self invoked)

## Function Return
When JavaScript reaches a return statement, the function will stop executing.

If the function was invoked from a statement, JavaScript will "return" to execute the code after the invoking statement.

Functions often compute a return value. The return value is "returned" back to the "caller":

## Why Functions?
You can reuse code: Define the code once, and use it many times.

You can use the same code many times with different arguments, to produce different results.

## Functions Used as Variable Values
Functions can be used the same way as you use variables, in all types of formulas, assignments, and calculations.

## Local Variables
Variables declared within a JavaScript function, become LOCAL to the function.

Local variables can only be accessed from within the function.

Since local variables are only recognized inside their functions, variables with the same name can be used in different functions.

Local variables are created when a function starts, and deleted when the function is completed.

# Pair Programming
Iterative loops. Code reviews. Fast feedback. Error checking and linting. These are software engineering practices that have proven to dramatically improve the quality of code developers produce. What if you can could get all of this, instantaneously, while typing code line by line and character by character? You can, with pair programming, a technique common to many agile work environments.

## How does pair programming work?
While there are many different styles, pair programming commonly involves two roles: the Driver and the Navigator. The Driver is the programmer who is typing and the only one whose hands are on the keyboard. Handling the “mechanics” of coding, the Driver manages the text editor, switching files, version control, and—of course writing—code. The Navigator uses their words to guide the Driver but does not provide any direct input to the computer. The Navigator thinks about the big picture, what comes next, how an algorithm might be converted in to code, while scanning for typos or bugs. The Navigator might also utilize their computer as a second screen to look up solutions and documentation, but should not be writing any code.

## Why pair program?
1. Greater efficiency

It is a common misconception that pair programming takes a lot longer and is less efficient.

2. Engaged collaboration

When two programmers focus on the same code, the experience is more engaging and both programmers are more focused than if they were working alone. 

3. Learning from fellow students

Everyone has a different approach to problem solving; working with a teammate can expose developers to techniques they otherwise would not have thought of.

4. Social skills

Pair programming is great for improving social skills. When working with someone who has a different coding style, communication is key.

5. Job interview readiness

A common step in many interview processes involves pair programming between a current employee and an applicant, either in person or through a shared screen.

6. Work environment readiness

Many companies that utilize pair programing expect to train fresh hires from CS-degree programs on how they operate to actually deliver a product.

# References
> JAVASCRIPT & JQUERY
Interactive Front-End Web Development
JON DUCKETT

> HTML & CSS
Design and Build Websites
Jon Ducket

> from https://www.w3schools.com/

> from https://www.codefellows.org/blog/6-reasons-for-pair-programming/
