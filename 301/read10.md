# Call stack
A call stack is a mechanism for an interpreter (like the JavaScript interpreter in a web browser) to keep track of its place in a script that calls multiple functions — what function is currently being run and what functions are called from within that function, etc.

* When a script calls a function, the interpreter adds it to the call stack and then starts carrying out the function.
* Any functions that are called by that function are added to the call stack further up, and run where their calls are reached.
* When the current function is finished, the interpreter takes it off the stack and resumes execution where it left off in the last code listing.
* If the stack takes up more space than it had assigned to it, it results in a "stack overflow" error.

## Example

![1](https://www4.0zz0.com/2021/04/28/19/780297796.png)

The code above would be executed like this:

1. Ignore all functions, until it reaches the greeting() function invocation.
2. Add the greeting() function to the call stack list
3. Execute all lines of code inside the greeting() function.
4. Get to the sayHi() function invocation.
5. Add the sayHi() function to the call stack list.
6. Execute all lines of code inside the sayHi() function, until reaches its end.
7. Return execution to the line that invoked sayHi() and continue executing the rest of the greeting() function.
8. Delete the sayHi() function from our call stack list
9. When everything inside the greeting() function has been executed, return to its invoking line to continue executing the rest of the JS code.
10. Delete the greeting() function from the call stack list

In summary, then, we start with an empty Call Stack. Whenever we invoke a function, it is automatically added to the Call Stack. Once the function has executed all of its code, it is automatically removed from the Call Stack. Ultimately, the Stack is empty again.

## The JavaScript Call Stack - What It Is and Why It's Necessary

The JavaScript engine (which is found in a hosting environment like the browser), is a single-threaded interpreter comprising of a heap and a single call stack. The browser provides web APIs like the DOM, AJAX, and Timers.

The call stack is primarily used for function invocation (call). Since the call stack is single, function(s) execution, is done, one at a time, from top to bottom. It means the call stack is synchronous

The understanding of the call stack is vital to Asynchronous programming

In Asynchronous JavaScript, we have a callback function, an event loop, and a task queue. The callback function is acted upon by the call stack during execution after the call back function has been pushed to the stack by the event loop.

But before we jump the gun, let us first attempt to answer the question - What is the call stack?

At the most basic level, a call stack is a data structure that uses the Last In, First Out (LIFO) principle to temporarily store and manage function invocation (call).

LIFO: When we say that the call stack, operates by the data structure principle of Last In, First Out, it means that the last function that gets pushed into the stack is the first to be pop out, when the function returns.

Let us take a look at a code sample to demonstrate LIFO by printing a stack trace error to the console.

![2](https://www9.0zz0.com/2021/04/28/19/632510315.png)

When the code is run, we get an error. A stack is printed showing how the functions are stack on top each other. Take a look at the diagram.

![3](https://cdn-media-1.freecodecamp.org/images/zOINLHPC8E56ac8yyINYOFWeImsjM2Wk2rdU)

ou will notice that the arrangement of the functions as a stack begins with the firstFunction() (which is the last function that got into the stack, and is popped out to throw the error), followed by the secondFunction(), and then the thirdFunction() (which is the first function that gets pushed into the stack when the code is executed).

Temporarily store: When a function is invoked (called), the function, its parameters, and variables are pushed into the call stack to form a stack frame. This stack frame is a memory location in the stack. The memory is cleared when the function returns as it is pop out of the stack.

![4](https://cdn-media-1.freecodecamp.org/images/QgR2uIk7tW0YNz0Xm8g0jAPeRFI0e4sCejsv)

Manage function invocation (call): The call stack maintains a record of the position of each stack frame. It knows the next function to be executed (and will remove it after execution). This is what makes code execution in JavaScript synchronous.

## How does the call stack handle function calls?

We will answer this question by looking at a sample code of a function that calls another function. Here is the example code:

![5](https://www5.0zz0.com/2021/04/28/19/895785920.png)

![6](https://cdn-media-1.freecodecamp.org/images/oEp65Ec9CD4CnL7t0uSPoyzrkA1i1BR-Ij1n)

This is what happens when the code is run:

1. When secondFunction() gets executed, an empty stack frame is created. It is the main (anonymous) entry point of the program.
2. secondFunction() then calls firstFunction()which is pushed into the stack.
3. firstFunction() returns and prints “Hello from firstFunction” to the console.
4. firstFunction() is pop off the stack.
5. The execution order then move to secondFunction().
6. secondFunction() returns and print “The end from secondFunction” to the console.
7. secondFunction() is pop off the stack, clearing the memory.

## What causes a stack overflow?
A stack overflow occurs when there is a recursive function (a function that calls itself) without an exit point. The browser (hosting environment) has a maximum stack call that it can accomodate before throwing a stack error.

Here is an example:

![7](https://www5.0zz0.com/2021/04/28/19/698300437.png)

The callMyself() will run until the browser throws a “Maximum call size exceeded”. And that is a stack overflow.

![8](https://cdn-media-1.freecodecamp.org/images/lvjT-ud6XfVQ5KYVWxZZWkKeVTgtJqFD0pWv)

# References

> https://developer.mozilla.org/en-US/docs/Glossary/Call_stack

> https://www.freecodecamp.org/news/understanding-the-javascript-call-stack-861e41ae61d4/