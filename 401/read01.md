# Big O Notation
Big O notation is used in Computer Science to describe the performance or complexity of an algorithm. Big O specifically describes the worst-case scenario, and can be used to describe the execution time required or the space used (e.g. in memory or on disk) by an algorithm.

The best way to understand Big O thoroughly was to produce some examples in code. So, below are some common orders of growth along with descriptions and examples where possible.

## O(1)

O(1) describes an algorithm that will always execute in the same time (or space) regardless of the size of the input data set.

`
bool IsFirstElementNull(IList<String> elements)
{
    return elements[0] == null;
}
`

## O(N)

O(N) describes an algorithm whose performance will grow linearly and in direct proportion to the size of the input data set. The example below also demonstrates how Big O favours the worst-case performance scenario; a matching string could be found during any iteration of the for loop and the function would return early, but Big O notation will always assume the upper limit where the algorithm will perform the maximum number of iterations.

`
bool ContainsValue(IEnumerable<string> elements, string value)
{
    foreach (var element in elements)
    {
        if (element == value) return true; 
    }     
    return false; 
}
`
## O(N²)

O(N²) represents an algorithm whose performance is directly proportional to the square of the size of the input data set. This is common with algorithms that involve nested iterations over the data set. Deeper nested iterations will result in O(N³), O(N⁴) etc.


bool ContainsDuplicates(IList<string> elements)
{
    for (var outer = 0; outer < elements.Count; outer++) 
    {
        for (var inner = 0; inner < elements.Count; inner++) 
        { 
            // Don't compare with self 
            if (outer == inner) continue;             
            
            if (elements[outer] == elements[inner]) return true; 
        }
    }    
    return false;
}

## O(2^N)

O(2^N) denotes an algorithm whose growth doubles with each addition to the input data set. The growth curve of an O(2^N) function is exponential — starting off very shallow, then rising meteorically. An example of an O(2^N) function is the recursive calculation of Fibonacci numbers:


int Fibonacci(int number)
{
    if (number <= 1) return number;
       
    return Fibonacci(number - 2) + Fibonacci(number - 1); 
}

## Logarithms

Binary search is a technique used to search sorted data sets. It works by selecting the middle element of the data set, essentially the median, and compares it against a target value. If the values match, it will return success. If the target value is higher than the value of the probe element, it will take the upper half of the data set and perform the same operation against it. Likewise, if the target value is lower than the value of the probe element, it will perform the operation against the lower half. It will continue to halve the data set with each iteration until the value has been found or until it can no longer split the data set.

This type of algorithm is described as O(log N). The iterative halving of data sets described in the binary search example produces a growth curve that peaks at the beginning and slowly flattens out as the size of the data sets increase e.g. an input data set containing 10 items takes one second to complete, a data set containing 100 items takes two seconds, and a data set containing 1,000 items will take three seconds. Doubling the size of the input data set has little effect on its growth as after a single iteration of the algorithm the data set will be halved and therefore on a par with an input data set half the size. This makes algorithms like binary search extremely efficient when dealing with large data sets.

# Facts and myths about Python names and values

The behavior of names and values in Python can be confusing. Like many parts of Python, it has an underlying simplicity that can be hard to discern, especially if you are used to other programming languages. Here I’ll explain how it all works, and present some facts and myths along the way.

As in many programming languages, a Python assignment statement associates a symbolic name on the left-hand side with a value on the right-hand side. In Python, we say that names refer to values, or a name is a reference to a value:

`x = 23`

Now the name “x” refers to the value 23. The next time we use the name x, we’ll get the value 23:

`print(x+2)       # prints 25`

Exactly how the name refers to the value isn’t really important. If you’re experienced with the C language, you might like to think of it as a pointer, but if that means nothing to you then don’t worry about it.

There’s no rule that says a value can only have one name. An assignment statement can make a second (or third, ...) name refer to the same value.

`
x = 23
y = x
`

Now x and y both refer to the same value

Neither x or y is the “real” name. They have equal status: each refers to the value in exactly the same way.

If two names refer to the same value, this doesn’t magically link the two names. Reassigning one of them won’t reassign the other also:

`
x = 23
y = x
x = 12
`

When we said “y = x”, that doesn’t mean that they will always be the same forever. Reassigning x leaves y alone. Imagine the chaos if it didn’t!

## Assignment

An important fact about assignment:

Fact: Assignment never copies data.

When values have more than one name, it’s easy to get confused and think of it as two names and two values:

`
x = 23
y = x
 "Now I have two values: x and y!"
 NO: you have two names, but only one value.
`
Assigning a value to a name never copies the data, it never makes a new value. Assignment just makes the name on the left refer to the value on the right. In this case, we have only one 23, and x and y both refer to it, just as we saw in the last diagrams.

Things get more interesting when we have more complicated values, like a list:

`nums = [1, 2, 3]`

Now if we assign nums to another name, we’ll have two names referring to the same list:

`
nums = [1, 2, 3]
tri = nums
`

Remember: assignment never makes new values, and it never copies data. This assignment statement doesn’t magically turn my list into two lists.

At this point, we have one list, referred to by two names, which can lead to a big surprise which is common enough I’m going to give it a catchy name: the Mutable Presto-Chango.

Fact: Changes in a value are visible through all of its names. (Mutable Presto-Chango)

Values fall into two categories based on their type: mutable or immutable. Immutable values include numbers, strings, and tuples. Almost everything else is mutable, including lists, dicts, and user-defined objects. Mutable means that the value has methods that can change the value in-place. Immutable means that the value can never change, instead when you think you are changing the value, you are really making new values from old ones.

Since numbers are immutable, you can’t change one in-place, you can only make a new value and assign it to the same name:

`
x = 1
`

`x = x + 1
`

Here, x+1 computes an entirely new value, which is then assigned to x.

With a mutable value, you can change the value directly, usually with a method on the value:

`nums = [1, 2, 3]`

`nums.append(4)`

