# Pythonisms
----
## Dunder Methods:
 emulate the behavior of built-in types. 
  For example, to get the length of a string you can call len('string'). But an empty class definition doesn’t support this behavior out of the box:
```
class NoLenSupport:
    pass

>>> obj = NoLenSupport()
>>> len(obj)
TypeError: "object of type 'NoLenSupport' has no len()"
```
* To fix this, you can add a __len__ dunder method to your class:
```
class LenSupport:
    def __len__(self):
        return 42

>>> obj = LenSupport()
>>> len(obj)
42
```
## Enriching a Simple Account Class
1. Object Initialization: __init__
```
class Account:
    """A simple account class"""

    def __init__(self, owner, amount=0):
        """
        This is the constructor that lets us create
        objects from this class
        """
        self.owner = owner
       
```
2. Object Representation: __str__, __repr__
* __repr__: The “official” string representation of an object. This is how you would make an object of the class. The goal of __repr__ is to be unambiguous.

* __str__: The “informal” or nicely printable string representation of an object. This is for the enduser.
```
class Account:
    # ... (see above)

    def __repr__(self):
        return 'Account({!r}, {!r})'.format(self.owner, self.amount)

    def __str__(self):
        return 'Account of {} with starting amount: {}'.format(
            self.owner, self.amount)
```
3. Iteration: __len__, __getitem__, __reversed__
```
def add_transaction(self, amount):
    if not isinstance(amount, int):
        raise ValueError('please use int for amount')
    self._transactions.append(amount)
```
4. Operator Overloading for Comparing Accounts: __eq__, __lt__
 functools.total_ordering decorator which allows me to take a shortcut, only implementing __eq__ and __lt__:
```
from functools import total_ordering

@total_ordering
class Account:
    # ... (see above)

    def __eq__(self, other):
        return self.balance == other.balance

    def __lt__(self, other):
        return self.balance < other.balance
```
5. Operator Overloading for Merging Accounts: __add__
The expected behavior would be to merge all attributes together
```
def __add__(self, other):
    owner = self.owner + other.owner
    start_amount = self.balance + other.balance
    return Account(owner, start_amount)
```
6. Callable Python Objects: __call__
the downside of having a __call__ method on your objects is that it can be hard to see what the purpose of calling the object is.

7. Context Manager Support and the With Statement: __enter__, __exit__

is a simple “protocol” (or interface) that your object needs to follow so it can be used with the with statement. Basically all you need to do is add __enter__ and __exit__ methods to an object if you want it to function as a context manager.
----
# Python Iterators: A Step-By-Step Introduction
* Python Iterators That Iterate Forever
We’ll begin by writing a class that demonstrates the bare-bones iterator protocol in Python.
 implement a class called Repeater that can be iterated over with a for-in loop, like so:
```
repeater = Repeater('Hello')
for item in repeater:
    print(item)
```
* How do for-in loops work in Python?
the for-in was just syntactic sugar for a simple while loop:
```
repeater = Repeater('Hello')
iterator = repeater.__iter__()
while True:
    item = iterator.__next__()
    print(item)
```

* It first prepared the repeater object for iteration by calling its __iter__ method. This returned the actual iterator object.
* After that, the loop repeatedly calls the iterator object’s __next__ method to retrieve values from it.

-----
# What Are Python Generators?
 what the class looked like in its second (simplified) version:
```
class Repeater:
    def __init__(self, value):
        self.value = value

    def __iter__(self):
        return self

    def __next__(self):
        return self.value
```
If I rewrite this iterator class as a generator, it looks like this:
```
def repeater(value):
    while True:
        yield value
```
* The yield statement allows you to temporarily suspend execution of a generator function and to pass back values from it.
* Generators start raising StopIteration exceptions after control flow leaves the generator function by any means other than a yield statement.