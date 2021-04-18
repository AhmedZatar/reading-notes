# jQuery
jQuery offers a simple way to achieve a variety of common
JavaScript tasks quickly and consistently, across all major
browsers and without any fallback code needed.

### Find elements using CSS-STYLE

![1](https://www8.0zz0.com/2021/04/18/22/765578998.png)

### Do something with the elements using JQUERY methods

![2](https://www8.0zz0.com/2021/04/19/00/764786008.png)

## A basic JQUERY example

![3](https://www9.0zz0.com/2021/04/19/00/839773404.png)

![4](https://www9.0zz0.com/2021/04/19/00/238218769.png)

![5](https://www9.0zz0.com/2021/04/19/00/381387785.png)

## WHY USE JQUERY? 

jQuery doesn't do anything you cannot achieve with pure JavaScript.
It is just a JavaScript file but estimates show it has been used on over a
quarter of the sites on the web, because it makes coding simpler. 

## jQuery Syntax

The jQuery syntax is tailor-made for selecting HTML elements and performing some action on the element(s)

Basic syntax is: $(selector).action()

* A $ sign to define/access jQuery
* A (selector) to "query (or find)" HTML elements
* A jQuery action() to be performed on the element(s)

![6](https://www2.0zz0.com/2021/04/19/00/965457476.png)

## UPDATING ELEMENTS 

1. html() : This method gives every element
in the matched set the same new
content. The new content may
include HTML. 
2. text() : This method gives every element
in the matched set the same new
text content. Any markup would
be shown as text
3. replaceWith() : This method replaces every
element in a matched set with
new content. It also returns the
replaced elements
4. remove() : This method removes all of the
elements in the matched set. 

## INSERTING ELEMENTS
1. before() : This method inserts content
before the selected element(s). 
2. after() : This method inserts content
after the selected element(s).
3. prepend() : This method inserts content
inside the selected element(s),
after the opening tag. 
4. append() : This method inserts content
inside the selected element(s),
before the closing tag.

## GETTING AND SETTING ATTRIBUTE VALUES
1. attr() : This method can get or set a
specified attribute and its value.
To get the value of an attribute,
you specify the name of the
attribute in the parentheses. 
2. removeAttr() : This method removes a specified
attribute (and its value). You just
specify the name of the attribute
that you want to remove from the
element in the parentheses. 
3. addClass() : This method adds a new value
to the existing value of the cl ass
attribute. It does not overwrite
existing values.
4. removeClass() : This method removes a value
from the cl ass attribute, leaving
any other class names within
that attribute intact. 
## GETTING & SETTING CSS PROPERTIES 
The .css() method lets you retrieve
and set the values of CSS properties. 

## WORKING WITH EACH ELEMENT IN A SELECTION 
jQuery allows you to recreate the functionality
of a loop on a selection of elements, using the
.each() method. 

## EVENT METHODS
The  .on() method is used to handle all events.
Behind the scenes, jQuery handles all of the
cross-browser issues you saw in the last chapter. 

## THE EVENT OBJECT
Every event handling function receives an event object.
It has methods and properties related to the event that occurred. 

![7](https://www3.0zz0.com/2021/04/19/00/482445185.png)

![8](https://www3.0zz0.com/2021/04/19/00/406735642.png)

# Pair Programming

## How does pair programming work?

While there are many different styles, pair programming commonly involves two roles: the Driver and the Navigator. The Driver is the programmer who is typing and the only one whose hands are on the keyboard. Handling the “mechanics” of coding, the Driver manages the text editor, switching files, version control, and—of course writing—code. The Navigator uses their words to guide the Driver but does not provide any direct input to the computer. The Navigator thinks about the big picture, what comes next, how an algorithm might be converted in to code, while scanning for typos or bugs. The Navigator might also utilize their computer as a second screen to look up solutions and documentation, but should not be writing any code.

## Why pair program?

### 1. Greater efficiency

It is a common misconception that pair programming takes a lot longer and is less efficient. In reality, when two people focus on the same code base, it is easier to catch mistakes in the making. Research indicates that pair programing takes slightly longer, but produces higher-quality code that doesn’t require later effort in troubleshooting and debugging (let alone exposing users to a broken product). So, in the long-run, it’s often actually more efficient than two people working on separate features. When coming up with ideas and discussing solutions out loud, two programmers may come to a solution faster than one programmer on their own. Also, when the pair is stuck, both programmers can research the problem and reach a solution faster. Researches also identified pairing enhances technical skills, team communication, and even enjoyability of coding in the workplace.

### 2. Engaged collaboration
When two programmers focus on the same code, the experience is more engaging and both programmers are more focused than if they were working alone. It is harder to procrastinate or get off track when someone else is relying on you to complete the work. Popping open your Facebook timeline is just that less enticing when someone else is looking at your screen.

### 3. Learning from fellow students
Everyone has a different approach to problem solving; working with a teammate can expose developers to techniques they otherwise would not have thought of. If one developer has a unique approach to a specific problem, pair programming exposes the other developer to a new solution.

### 4. Social skills
Pair programming is great for improving social skills. When working with someone who has a different coding style, communication is key. This can become more difficult when two programmers have different personalities. Pair programming not only improves programming skills, but can also help programmers develop their interpersonal skills. When just grabbing the keyboard and taking over isn’t an option, getting good at finding the right words is a skill unto itself

### 5. Job interview readiness
A common step in many interview processes involves pair programming between a current employee and an applicant, either in person or through a shared screen. They will carry out exercises together, such as code challenges, building a project or feature, or debugging an existing code base. By doing so, companies can get a better feel for how an applicant will fit into the team and their collaboration style.

### 6. Work environment readiness
Many companies that utilize pair programing expect to train fresh hires from CS-degree programs on how they operate to actually deliver a product. Code Fellows graduates who are already familiar with how pairing works can hit the ground running at a new job, with one less hurdle to overcome.

 # References

> JAVASCRIPT & JQUERY
Interactive Front-End Web Development
JON DUCKETT

> https://www.codefellows.org/blog/6-reasons-for-pair-programming/

