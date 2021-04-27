# Functional Programming
## What is functional programming?
Functional programming is a programming paradigm — a style of building the structure and elements of computer programs — that treats computation as the evaluation of mathematical functions and avoids changing-state and mutable

## Pure functions
The first fundamental concept we learn when we want to understand functional programming is pure functions. But what does that really mean? What makes a function pure?

So how do we know if a function is pure or not? Here is a very strict definition of purity:

* It returns the same result if given the same arguments (it is also referred as deterministic)
* It does not cause any observable side effects

### It returns the same result if given the same arguments
Imagine we want to implement a function that calculates the area of a circle. An impure function would receive radius as the parameter, and then calculate radius * radius * PI:


`let PI = 3.14;
const calculateArea = (radius) => radius * radius * PI;
calculateArea(10); // returns 314.0`

Why is this an impure function? Simply because it uses a global object that was not passed as a parameter to the function.

Now imagine some mathematicians argue that the PI value is actually 42and change the value of the global object.

Our impure function will now result in 10 * 10 * 42 = 4200. For the same parameter (radius = 10), we have a different result. Let's fix it!

`let PI = 3.14;
const calculateArea = (radius, pi) => radius * radius * pi;
calculateArea(10, PI); // returns 314.0`

Now we’ll always pass thePI value as a parameter to the function. So now we are just accessing parameters passed to the function. No external object.

* For the parameters radius = 10 & PI = 3.14, we will always have the same the result: 314.0
* For the parameters radius = 10 & PI = 42, we will always have the same the result: 420

### Reading Files

If our function reads external files, it’s not a pure function — the file’s contents can change.

### Random number generation

Any function that relies on a random number generator cannot be pure.


### It does not cause any observable side effects

Examples of observable side effects include modifying a global object or a parameter passed by reference.

Now we want to implement a function to receive an integer value and return the value increased by 1.

We have the counter value. Our impure function receives that value and re-assigns the counter with the value increased by 1.

Observation: mutability is discouraged in functional programming.
We are modifying the global object. But how would we make it pure? Just return the value increased by 1. Simple as that.

See that our pure function increaseCounter returns 2, but the counter value is still the same. The function returns the incremented value without altering the value of the variable.

If we follow these two simple rules, it gets easier to understand our programs. Now every function is isolated and unable to impact other parts of our system.

Pure functions are stable, consistent, and predictable. Given the same parameters, pure functions will always return the same result. We don’t need to think of situations when the same parameter has different results — because it will never happen.

## Pure functions benefits

The code’s definitely easier to test. We don’t need to mock anything. So we can unit test pure functions with different contexts:

* Given a parameter A → expect the function to return value B
* Given a parameter C → expect the function to return value D


## Immutability
Unchanging over time or unable to be changed.

When data is immutable, its state cannot change after it’s created. If you want to change an immutable object, you can’t. Instead, you create a new object with the new value.

In Javascript we commonly use the for loop. This next for statement has some mutable variables.

We can handle this mutation by doing function composition, or function chaining. 

Here we have:


* toLowerCase: converts the string to all lower case
* trim: removes whitespace from both ends of a string
* split and join: replaces all instances of match with replacement in a given string

## Referential transparency
Basically, if a function consistently yields the same result for the same input, it is referentially transparent

`Basically, if a function consistently yields the same result for the same input, it is referentially transparent`

## Functions as first-class entities
The idea of functions as first-class entities is that functions are also treated as values and used as data.

Functions as first-class entities can:
* refer to it from constants and variables
* pass it as a parameter to other functions
* return it as result from other functions

The idea is to treat functions as values and pass functions like data. This way we can combine different functions to create new functions with new behavior.

## Higher-order functions
When we talk about higher-order functions, we mean a function that either:

* takes one or more functions as arguments, or
* returns a function as its result

The doubleOperator function we implemented above is a higher-order function because it takes an operator function as an argument and uses it.

You’ve probably already heard about filter, map, and reduce. Let's take a look at these.

## Map
The idea of map is to transform a collection.

The map method transforms a collection by applying a function to all of its elements and building a new collection from the returned values.

## Reduce

The idea of reduce is to receive a function and a collection, and return a value created by combining the items.

# References

> https://medium.com/the-renaissance-developer/concepts-of-functional-programming-in-javascript-6bc84220d2aa

