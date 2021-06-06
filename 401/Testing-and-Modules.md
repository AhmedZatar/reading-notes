# TDD with Python

## Unit tests and TDD
Unit tests are some pieces of code to exercise the input, the output and the behaviour of your code. You can write them anytime you want.

But Test-Driven Development is a strategy to think (and write!) tests first.

## The freela

Imagine that a client has a website and through it he receives a lot of contacts from potential customers. After a while he realized that it is important for the business to identify the profile of consumer: age, gender, job and so on. But the website just receive the name and the email.

They hired you to identify the gender of a person based on his/her name. Luckily, there is an amazing API called Genderize.io that identifies the possible genders. And you quickly developed your API connection:

`requests.get('https://api.genderize.io/?name=ana')`

However the client demands you to write unit tests and you are curious about TDD. Here our journey begins!

The API is pretty straightforward and your work was almost done. But with TDD we need to think about tests first. And to be ok with the possibility of the beginning to be hard sometimes

Coming back to the code and thinking with baby steps, what is the smaller test that we can do against a function (method/class) that will return the gender?

Input: Ana [name]

Output: female [gender]

![1](https://www9.0zz0.com/2021/06/06/17/352585199.png)

There are some details to pay attention. The first one is the test name. The tests can be considered as your alive documentation. We need to be descriptive about it and to say what is expected and what we are testing. In this case we explicitly said: should return female when the name is from a female.

The test file name should follow the same name of module name. For instance, if our module is gender.py, our test name should be test_gender.py. It’s ideal to separate the tests folder from production code (the implementation) and to have something like this:

![2](https://www4.0zz0.com/2021/06/06/17/493802581.png)


Other thing to care about is the structure. A convention widely used is the AAA: Arrange, Act and Assert.
* Arrange: you need to organize the data needed to execute that piece of code (input);
* Act: here you will execute the code being tested (exercise the behaviour);
* Assert: after executing the code, you will check if the result (output) is the same as you were expecting.

Now you can execute the tests. I suggest the lib pytest to do it. But you are free to choose anything you like.

## The Cycle

The cycle is made by three steps:

* Write a unit test and make it fail (it needs to fail because the feature isn’t there, right? If this test passes, call the Ghostbusters, really)
* Write the feature and make the test pass! (you can dance after that)
* Refactor the code — the first version doesn’t need to be the beautiful one (don’t be shy)

We just need to write the method that returns the right answer: FEMALE!

![3](https://www12.0zz0.com/2021/06/06/17/632463800.png)

## TDD is not about the money/tests

More than any checking, we need to think about our software design first.

One of the things that amaze me about TDD is how we can grow our software design consciously and well, just building what is needed to make the test pass. When we are writing tests we are forced to think about the design first and how we can break it into small pieces.

Let’s write one more test. Besides female names, we need to identify male names as well.

![4](https://www9.0zz0.com/2021/06/06/17/557575259.png)

But when we run it will fail because we just return female, right? Let’s fix it using our real code.

![5](https://www9.0zz0.com/2021/06/06/17/160207702.png)

Now our tests are passing

![6](https://miro.medium.com/max/700/1*gxEKnrQuS7CO3hONTD7_hg.png)

# Recursion

## What is Recursion? 
The process in which a function calls itself directly or indirectly is called recursion and the corresponding function is called as recursive function. Using recursive algorithm, certain problems can be solved quite easily.

A Mathematical Interpretation

Let us consider a problem that a programmer have to determine the sum of first n natural numbers, there are several ways of doing that but the simplest approach is simply add the numbers starting from 1 to n. So the function simply looks like

![7](https://www3.0zz0.com/2021/06/06/17/196405554.png)

but there is another mathematical approach of representing this,

![8](https://www3.0zz0.com/2021/06/06/17/663561776.png)

There is a simple difference between the approach (1) and approach(2) and that is in approach(2) the function “ f( ) ” itself is being called inside the function, so this phenomenon is named as recursion and the function containing recursion is called recursive function, at the end this is a great tool in the hand of the programmers to code some problems in a lot easier and efficient way.


### What is base condition in recursion?
In the recursive program, the solution to the base case is provided and the solution of the bigger problem is expressed in terms of smaller problems. 

![9](https://www3.0zz0.com/2021/06/06/17/331185698.png)

In the above example, base case for n < = 1 is defined and larger value of number can be solved by converting to smaller one till base case is reached.

### How a particular problem is solved using recursion? 
The idea is to represent a problem in terms of one or more smaller problems, and add one or more base conditions that stop the recursion. For example, we compute factorial n if we know factorial of (n-1). The base case for factorial would be n = 0. We return 1 when n = 0. 

### Why Stack Overflow error occurs in recursion? 
If the base case is not reached or not defined, then the stack overflow problem may arise. Let us take an example to understand this.

![10](https://www9.0zz0.com/2021/06/06/17/404869419.png)

If fact(10) is called, it will call fact(9), fact(8), fact(7) and so on but the number will never reach 100. So, the base case is not reached. If the memory is exhausted by these functions on the stack, it will cause a stack overflow error. 

What is the difference between direct and indirect recursion? 
A function fun is called direct recursive if it calls the same function fun. A function fun is called indirect recursive if it calls another function say fun_new and fun_new calls fun directly or indirectly.

### What is difference between tailed and non-tailed recursion? 
A recursive function is tail recursive when recursive call is the last thing executed by the function.