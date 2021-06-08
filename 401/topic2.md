# Classes and Objects
Objects are an encapsulation of variables and functions into a single entity. Objects get their variables and functions from classes. Classes are essentially a template to create your objects.

A very basic class would look something like this:

![0](https://www4.0zz0.com/2021/06/08/21/761923799.png)

We'll explain why you have to include that "self" as a parameter a little bit later. First, to assign the above class(template) to an object you would do the following:

![1](https://www10.0zz0.com/2021/06/08/21/125422246.png)

Now the variable "myobjectx" holds an object of the class "MyClass" that contains the variable and the function defined within the class called "MyClass".

## Accessing Object Variables
To access the variable inside of the newly created object "myobjectx" you would do the following:

![2](https://www10.0zz0.com/2021/06/08/21/833430493.png)

So for instance the below would output the string "blah":

![3](https://www4.0zz0.com/2021/06/08/21/366161134.png)

You can create multiple different objects that are of the same class(have the same variables and functions defined). However, each object contains independent copies of the variables defined in the class. For instance, if we were to define another object with the "MyClass" class and then change the string in the variable above:

![4](https://www14.0zz0.com/2021/06/08/21/237665819.png)

## Accessing Object Functions
To access a function inside of an object you use notation similar to accessing a variable:

![5](https://www9.0zz0.com/2021/06/08/21/219993066.png)

The above would print out the message, "This is a message inside the class."

# Thinking Recursively in Python
Problems (in life and also in computer science) can often seem big and scary. But if we keep chipping away at them, more often than not we can break them down into smaller chunks trivial enough to solve. This is the essence of thinking recursively, and my aim in this article is to provide you, my dear reader, with the conceptual tools necessary to approach problems from this recursive point of view.

Have you ever wondered how Christmas presents are delivered? I sure have, and I believe Santa Claus has a list of houses he loops through. He goes to a house, drops off the presents, eats the cookies and milk, and moves on to the next house on the list. Since this algorithm for delivering presents is based on an explicit loop construction, it is called an iterative algorithm.



The algorithm for iterative present delivery implemented in Python:

```
houses = ["Eric's house", "Kenny's house", "Kyle's house", "Stan's house"]

def deliver_presents_iteratively():
    for house in houses:
        print("Delivering presents to", house)
```
```
>>> deliver_presents_iteratively()
Delivering presents to Eric's house
Delivering presents to Kenny's house
Delivering presents to Kyle's house
Delivering presents to Stan's house
```
But I feel for Santa. At his age, he shouldn’t have to deliver all the presents by himself. I propose an algorithm with which he can divide the work of delivering presents among his elves:

![6](https://robocrop.realpython.net/?url=https%3A//files.realpython.com/media/elves_7.8d1af1cd85c8.png&w=1918&sig=24bad525e070e8248cc8fcce28fc3f52c68a69f9)

This is the typical structure of a recursive algorithm. If the current problem represents a simple case, solve it. If not, divide it into subproblems and apply the same strategy to them.

The algorithm for recursive present delivery implemented in Python:

```
houses = ["Eric's house", "Kenny's house", "Kyle's house", "Stan's house"]

# Each function call represents an elf doing his work 
def deliver_presents_recursively(houses):
    # Worker elf doing his work
    if len(houses) == 1:
        house = houses[0]
        print("Delivering presents to", house)

    # Manager elf doing his work
    else:
        mid = len(houses) // 2
        first_half = houses[:mid]
        second_half = houses[mid:]

        # Divides his work among two elves
        deliver_presents_recursively(first_half)
        deliver_presents_recursively(second_half)
```

```
>>> deliver_presents_recursively(houses)
Delivering presents to Eric's house
Delivering presents to Kenny's house
Delivering presents to Kyle's house
Delivering presents to Stan's house
```

## Recursive Functions in Python
Now that we have some intuition about recursion, let’s introduce the formal definition of a recursive function. A recursive function is a function defined in terms of itself via self-referential expressions.

This means that the function will continue to call itself and repeat its behavior until some condition is met to return a result. All recursive functions share a common structure made up of two parts: base case and recursive case.

To demonstrate this structure, let’s write a recursive function for calculating n!:

1. Decompose the original problem into simpler instances of the same problem. This is the recursive case:

```
n! = n x (n−1) x (n−2) x (n−3) ⋅⋅⋅⋅ x 3 x 2 x 1
n! = n x (n−1)!
```

2. As the large problem is broken down into successively less complex ones, those subproblems must eventually become so simple that they can be solved without further subdivision. This is the base case:

```
n! = n x (n−1)! 
n! = n x (n−1) x (n−2)!
n! = n x (n−1) x (n−2) x (n−3)!
⋅
⋅
n! = n x (n−1) x (n−2) x (n−3) ⋅⋅⋅⋅ x 3!
n! = n x (n−1) x (n−2) x (n−3) ⋅⋅⋅⋅ x 3 x 2!
n! = n x (n−1) x (n−2) x (n−3) ⋅⋅⋅⋅ x 3 x 2 x 1!
```

Here, 1! is our base case, and it equals 1.

Recursive function for calculating n! implemented in Python:

```
def factorial_recursive(n):
    # Base case: 1! = 1
    if n == 1:
        return 1

    # Recursive case: n! = n * (n-1)!
    else:
        return n * factorial_recursive(n-1)
```
```
>>> factorial_recursive(5)
120
```
Behind the scenes, each recursive call adds a stack frame (containing its execution context) to the call stack until we reach the base case. Then, the stack begins to unwind as each call returns its results:

![7](https://files.realpython.com/media/stack.9c4ba62929cf.gif)

## Maintaining State
When dealing with recursive functions, keep in mind that each recursive call has its own execution context, so to maintain state during recursion you have to either:

* Thread the state through each recursive call so that the current state is part of the current call’s execution context
* Keep the state in global scope

A demonstration should make things clearer. Let’s calculate 1 + 2 + 3 ⋅⋅⋅⋅ + 10 using recursion. The state that we have to maintain is (current number we are adding, accumulated sum till now).

Here’s how you do that by threading it through each recursive call (i.e. passing the updated current state to each recursive call as arguments):

```
def sum_recursive(current_number, accumulated_sum):
    # Base case
    # Return the final state
    if current_number == 11:
        return accumulated_sum

    # Recursive case
    # Thread the state through the recursive call
    else:
        return sum_recursive(current_number + 1, accumulated_sum + current_number)

```
```
# Pass the initial state
>>> sum_recursive(1, 0)
55
```

Here’s how you maintain the state by keeping it in global scope:

```
# Global mutable state
current_number = 1
accumulated_sum = 0


def sum_recursive():
    global current_number
    global accumulated_sum
    # Base case
    if current_number == 11:
        return accumulated_sum
    # Recursive case
    else:
        accumulated_sum = accumulated_sum + current_number
        current_number = current_number + 1
        return sum_recursive()
```
```
>>> sum_recursive()
55
```
# Python Testing with pytest: Fixtures and Coverage

## Fixtures

When you're writing tests, you're rarely going to write just one or two. Rather, you're going to write an entire "test suite", with each test aiming to check a different path through your code. In many cases, this means you'll have a few tests with similar characteristics, something that pytest handles with "parametrized tests".

But in other cases, things are a bit more complex. You'll want to have some objects available to all of your tests. Those objects might contain data you want to share across tests, or they might involve the network or filesystem. These are often known as "fixtures" in the testing world, and they take a variety of different forms.

In pytest, you define fixtures using a combination of the pytest.fixture decorator, along with a function definition. For example, say you have a file that returns a list of lines from a file, in which each line is reversed:

```
def reverse_lines(f):
   return [one_line.rstrip()[::-1] + '\n'
           for one_line in f]
```
Note that in order to avoid the newline character from being placed at the start of the line, you remove it from the string before reversing and then add a '\n' in each returned string. Also note that although it probably would be a good idea to use a generator expression rather than a list comprehension, I'm trying to keep things relatively simple here.

If you're going to test this function, you'll need to pass it a file-like object. In my last article, I showed how you could use a StringIO object for such a thing, and that remains the case. But rather than defining global variables in your test file, you can create a fixture that'll provide your test with the appropriate object at the right time.

Here's how that looks in pytest:


```
@pytest.fixture
def simple_file():
   return StringIO('\n'.join(['abc', 'def', 'ghi', 'jkl']))
```
On the face of it, this looks like a simple function—one that returns the value you'll want to use later. And in many ways, it's similar to what you'd get if you were to define a global variable by the name of "simple_file".

## Coverage

This is all great, but if you've ever done any testing, you know there's always the question of how thoroughly you have tested your code. After all, let's say you've written five functions, and that you've written tests for all of them. Can you be sure you've actually tested all of the possible paths through those functions?

For example, let's assume you have a very strange function, only_odd_mul, which multiplies only odd numbers:

``` 
def only_odd_mul(x, y):
   if x%2 and y%2:
       return x * y
   else:
       raise NoEvenNumbersHereException(f'{x} and/or {y}
 ↪not odd')

```

Here's a test you can run on it:

```
def test_odd_numbers():
   assert only_odd_mul(3, 5) == 15
```

Sure enough, the test passed. It works great! The software is terrific!

Oh, but wait—as you've probably noticed, that wasn't a very good job of testing it. There are ways in which the function could give a totally different result (for example, raise an exception) that the test didn't check.

Perhaps it's easy to see it in this example, but when software gets larger and more complex, it's not going to be so easy to eyeball it. That where you want to have "code coverage", checking that your tests have run all of the code.

Now, 100% code coverage doesn't mean that your code is perfect or that it lacks bugs. But it does give you a greater degree of confidence in the code and the fact that it has been run at least once.

