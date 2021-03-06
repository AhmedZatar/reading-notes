# Understanding The Problem Domain Is The Hardest Part Of Programming
What is the hardest thing about writing code?

There are many common answers to this question:

* Learning a new technology
* Naming things
* Testing your code
* Debugging
* Fixing bugs
* Making software maintainable

## A familiar problem
In a good portion of my Pluralsight courses I show the viewer how to build the “Protein Tracker” application.

Protein Tracker is a simple example of an application that could be easily understood and implemented.

The idea behind the Protein Tracker application is that it allows a user to set a goal for the amount of protein to consume in a day.  The user can add protein amounts which are added to a total protein count that is tracked for that user.

Very simple functionality, easily explainable, but most importantly, easily understood.

![10](https://spzone-simpleprogrammer.netdna-ssl.com/wp-content/uploads/2013/07/Protein_Tracker_2013-07-03_16-44-41_thumb.png)

## Why problem domains are hard
The big issue is that many problem domains are like a puzzle with a blurry picture or no picture at all.

As programmers, we also are often not given complete information about the problem domain, so we don’t even have the information we need to understand it.

## What can you do about it?

If understanding the problem domain is the hardest part of programming and you want to make programming easier, you can do one of two things:

1. Make the problem domain easier

You can often make the problem domain easier by cutting out cases and narrowing your focus to a particular part of the problem.

2. Get better at understanding the problem domain

It is easy to fall into the trap of thinking you understand enough of the problem to get started coding it. 



# Document Object Model
The Document Object Model (DOM) specifies
how browsers should create a model of an HTML
page and how JavaScript can access and update the
contents of a web page while it is in the browser window. 

## THE DOM TREE IS A MODEL OF A WEB PAGE 
As a browser loads a web page, it creates a model of that page.
The model is called a DOM tree, and it is stored in the browsers' memory.
It consists of four main types of nodes. 

![1](https://www6.0zz0.com/2021/03/06/16/366840287.png)

## DOM TREE 

![2](https://www5.0zz0.com/2021/03/06/16/738411895.png)

## WORKING WITH THE DOM TREE 
Accessing and updating the DOM tree involves two steps: 
1. Locate the node that represents the element you want to work with.
2. Use its text content, child elements, and attributes. 

### STEP 1: ACCESS THE ELEMENTS 

![3](https://www6.0zz0.com/2021/03/06/17/663340924.png)

### STEP 2: WORK W ITH THOSE ELEMENTS 

![4](https://www6.0zz0.com/2021/03/06/17/210067157.png)

## ACCESSING ELEMENTS 

METHODS THAT RETURN A SINGLE ELEMENT NODE: 

![5](https://www9.0zz0.com/2021/03/06/17/144419197.png)

METHODS THAT RETURN ONE OR MORE ELEMENTS (AS A NODELIST): 

![6](https://www9.0zz0.com/2021/03/06/17/944851520.png)

## TRAVERSING THE DOM
When you have an element node, you can select
another element in relation to it using these five
properties. This is known as traversing the DOM. 

* parentNode

This property finds the element
node for the containing (or
parent) element in the HTML. 

* previousSibling & nextSibling

These properties find the
previous or next sibling of a node
if there are siblings. 


* firstChild & lastChild 

These properties find the first or
last child of the current element.

![7](https://www3.0zz0.com/2021/03/06/17/167984246.png)

## WHITESPACE NODES 
Traversing the DOM can be difficult because
some browsers add a text node whenever they
come across whitespace between elements. 

![9](https://www2.0zz0.com/2021/03/06/17/701741606.png)



