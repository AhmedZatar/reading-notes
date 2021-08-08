# Enriching Your Python Classes With Dunder (Magic, Special) Methods

What Python’s “magic methods” are and how you would use them to make a simple account class more Pythonic.

## What Are Dunder Methods?

In Python, special methods are a set of predefined methods you can use to enrich your classes. They are easy to recognize because they start and end with double underscores, for example __init__ or __str__.

As it quickly became tiresome to say under-under-method-under-under Pythonistas adopted the term “dunder methods”, a short form of “double under.”

These “dunders” or “special methods” in Python are also sometimes called “magic methods.” But using this terminology can make them seem more complicated than they really are

Dunder methods let you emulate the behavior of built-in types. For example, to get the length of a string you can call len('string'). But an empty class definition doesn’t support this behavior out of the box:

```
class NoLenSupport:
    pass

>>> obj = NoLenSupport()
>>> len(obj)
TypeError: "object of type 'NoLenSupport' has no len()"
```

To fix this, you can add a __ len __ dunder method to your class:

```
class LenSupport:
    def __len__(self):
        return 42

>>> obj = LenSupport()
>>> len(obj)
42
```

Another example is slicing. You can implement a __ getitem __ method which allows you to use Python’s list slicing syntax: obj[start:stop].

## Special Methods and the Python Data Model

This elegant design is known as the Python data model and lets developers tap into rich language features like sequences, iteration, operator overloading, attribute access, etc.

## Enriching a Simple Account Class

Throughout this article I will enrich a simple Python class with various dunder methods to unlock the following language features:

* Initialization of new objects
* Object representation
* Enable iteration
* Operator overloading (comparison)
* Operator overloading (addition)
* Method invocation
* Context manager support (with statement)

## Object Initialization: __init__

Right upon starting my class I already need a special method. To construct account objects from the Account class I need a constructor which in Python is the __init__ dunder:

```
class Account:
    """A simple account class"""

    def __init__(self, owner, amount=0):
        """
        This is the constructor that lets us create
        objects from this class
        """
        self.owner = owner
        self.amount = amount
        self._transactions = []

```

The constructor takes care of setting up the object. In this case it receives the owner name, an optional start amount and defines an internal transactions list to keep track of deposits and withdrawals.

This allows us to create new accounts like this:

```
>>> acc = Account('bob')  # default amount = 0
>>> acc = Account('bob', 10)
```

## Object Representation: __str__, __repr__

1. __repr__: The “official” string representation of an object. This is how you would make an object of the class. The goal of __repr__ is to be unambiguous.

2. __str__: The “informal” or nicely printable string representation of an object. This is for the enduser.

Let’s implement these two methods on the Account class:

```
class Account:
    # ... (see above)

    def __repr__(self):
        return 'Account({!r}, {!r})'.format(self.owner, self.amount)

    def __str__(self):
        return 'Account of {} with starting amount: {}'.format(
            self.owner, self.amount)

```

```
>>> str(acc)
'Account of bob with starting amount: 10'

>>> print(acc)
"Account of bob with starting amount: 10"

>>> repr(acc)
"Account('bob', 10)"

```

## Iteration: __len__, __getitem__, __reversed__

In order to iterate over our account object I need to add some transactions. So first, I’ll define a simple method to add transactions. I’ll keep it simple because this is just setup code to explain dunder methods, and not a production-ready accounting system:

```
def add_transaction(self, amount):
    if not isinstance(amount, int):
        raise ValueError('please use int for amount')
    self._transactions.append(amount)
```

I also defined a property to calculate the balance on the account so I can conveniently access it with account.balance. This method takes the start amount and adds a sum of all the transactions:

```
@property
def balance(self):
    return self.amount + sum(self._transactions)
```

Let’s do some deposits and withdrawals on the account:

```
>>> acc = Account('bob', 10)

>>> acc.add_transaction(20)
>>> acc.add_transaction(-10)
>>> acc.add_transaction(50)
>>> acc.add_transaction(-20)
>>> acc.add_transaction(30)

>>> acc.balance
80
```

Now I have some data and I want to know:

1. How many transactions were there?

2. Index the account object to get transaction number …

3. Loop over the transactions

With the class definition I have this is currently not possible. All of the following statements raise TypeError exceptions:

```
>>> len(acc)
TypeError

>>> for t in acc:
...    print(t)
TypeError

>>> acc[1]
TypeError
```