# Enriching Your Python Classes With Dunder (Magic, Special) Methods

What Python’s “magic methods” are and how you would use them to make a simple account class more Pythonic.
__________________________________________
### What Are Dunder Methods?
In Python, special methods are a set of predefined methods you can use to enrich your classes. They are easy to recognize because they start and end with double underscores, for example __init__ or __str__.

These “dunders” or “special methods” in Python are also sometimes called “magic methods.”

* Dunder methods let you emulate the behavior of built-in types. For example, to get the length of a string you can call len('string').
```
class NoLenSupport:
    pass

>>> obj = NoLenSupport()
>>> len(obj)
TypeError: "object of type 'NoLenSupport' has no len()"
```
To fix this, you can add a __len__ dunder method to your class:

class LenSupport:
```
    def __len__(self):
        return 42

>>> obj = LenSupport()
>>> len(obj)
```
__________________________________________
## Special Methods and the Python Data Model
You can see Python’s data model as a powerful API you can interface with by implementing one or more dunder methods. 
__________________________________________
## Enriching a Simple Account Class
Throughout this article I will enrich a simple Python class with various dunder methods to unlock the following language features:

* Initialization of new objects
* Object representation
* Enable iteration
* Operator overloading (comparison)
* Operator overloading (addition)
* Method invocation
* Context manager support (with statement)
__________________________________________
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
__________________________________________
## Object Representation: __str__, __repr__
It’s common practice in Python to provide a string representation of your object for the consumer of your class (a bit like API documentation.) There are two ways to do this using dunder methods:

* __repr__: The “official” string representation of an object. This is how you would make an object of the class. The goal of __repr__ is to be unambiguous.

* __str__: The “informal” or nicely printable string representation of an object. This is for the enduser.
__________________________________________
## Iteration: __len__, __getitem__, __reversed__
In order to iterate over our account object I need to add some transactions

__________________________________________
## Operator Overloading for Comparing Accounts: __eq__, __lt__

This polymorphic behavior is possible because these objects implement one or more comparison dunder methods.
An easy way to verify this is to use the dir() builtin:
```
>>> dir('a')
['__add__',
...
'__eq__',    <---------------
'__format__',
'__ge__',    <---------------
'__getattribute__',
'__getitem__',
'__getnewargs__',
'__gt__',    <---------------
...]
```
___________________________________________
## Operator Overloading for Merging Accounts: __add__
In Python, everything is an object. We are completely fine adding two integers or two strings with the + (plus) operator, it behaves in expected ways:
```
>>> dir(1)
[...
'__add__',
...
'__radd__',
...]
```
________________________________________
## Callable Python Objects: __call__
You can make an object callable like a regular function by adding the __call__ dunder method. 
```
class Account:
    # ... (see above)

    def __call__(self):
        print('Start amount: {}'.format(self.amount))
        print('Transactions: ')
        for transaction in self:
            print(transaction)
        print('\nBalance: {}'.format(self.balance))
```
____________________________________________
## Context Manager Support and the With Statement: __enter__, __exit__
My final example in this tutorial is about a slightly more advanced concept in Python: Context managers and adding support for the with statement.

## Tutorial: Basic Statistics in Python — Probability
## Prerequisites:
Similar to the previous post, this article assumes no prior knowledge of statistics, but does require at least a general knowledge of Python and general data science worflows.

### What is probability?

* Prerequisites:
 If you are uncomfortable with for loops and lists, I recommend covering them briefly in our free introductory Python course before progressing.

What is probability?
An event is some outcome of interest.The quintessential representation of probability is the humble coin toss.
![coin](https://i.imgur.com/GtbawRt.jpg)
 In a coin toss the only events that can happen are:

1. Flipping a heads
2. Flipping a tails
These two events form the sample space, the set of all possible events that can happen. To calculate the probability of an event occurring

### From statistics to probability
Our data will be generated by flipping a coin 10 times and counting how many times we get heads.

### The data and the distribution
The normal distribution refers to a particularly important phenomenon in the realm of probability and statistics.
 ![](https://i.imgur.com/3vDS2Au.png)

 ### Revisiting the normal

The normal distribution is significant to probability and statistics thanks to two factors: 
1. the Central Limit Theorem 
If we make many estimates, the Central Limit Theorem dictates that the distribution of these estimates will look like a normal distribution.

2. the Three Sigma Rule.
The Three Sigma rule, also known as the empirical rule or 68-95-99.7 rule, is an expression of how many of our observations fall within a certain distance of the mean,The Three Sigma rule dictates that given a normal distribution,
![mcs](https://i.imgur.com/Mt3RyE0.png)

3. Z-score
The Z-score is a simple calculation that answers the question, “Given a data point, how many standard deviations is it away from the mean?” The equation below is the Z-score equation.
![test](https://i.imgur.com/3TuDF4G.jpg)


