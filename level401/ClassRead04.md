# Classes and Objects

Class -- a blueprint for objects. A class is a user-defined type that describes what a certain type of object will look like. A class description consists of a declaration and a definition. Usually these pieces are split into separate files.

Object -- an encapsulation of data along with functions that act upon that data.
![class](https://intellipaat.com/mediaFiles/2019/03/python10.png)

## Some points on Python class: 
* Using the keyword class, classes are created.

* Attributes are the variables that are specific to the class you created.

* These attributes are always public and can be accessed by inserting a dot after the class name. For instance, “ClassName. AttributeName” will return the specific attribute detail for that class.

Advantages of using Classes in Python
* Classes help you in keeping all of the various types of data properly organised in one place. 

* Using classes enables you to take advantage of another OOP paradigm known as inheritance. This occurs when one class inherits the properties of another.
* Classes give you the ability to override any standard operators.
* Classes make your code reusable, which improves the efficiency of your programme.

```
class MyClass:
    variable = "blah"

    def function(self):
        print("This is a message inside the class.")
```
# Objects in Python
An object is simply a subclass of any class you’ve defined. When you create a class, an automatic instance is created. 

There are three main features in an object:
· State: This refers to the different attributes and properties of every object.

· Behaviour: This essentially indicates the object’s methods. It also reflects the interaction or response to other objects by this particular object.

· Identity: Identity is the unique name of the object to be invoked as needed.

```
class MyClass:
    variable = "blah"

    def function(self):
        print("This is a message inside the class.")

myobjectx = MyClass()

myobjectx.variable

```
# Python Testing with pytest: Fixtures and Coverage

Pytest is a python based testing framework, which is used to write and execute test codes. In the present days of REST services
![n](https://files.realpython.com/media/Getting-Started-with-Testing-in-Python_Watermarked.9f22be97343d.jpg)

# Coverage

This is all great, but if you've ever done any testing, you know there's always the question of how thoroughly you have tested your code.

* let's assume you have a very strange function, only_odd_mul:
```
def only_odd_mul(x, y):
   if x%2 and y%2:
       return x * y
   else:
       raise NoEvenNumbersHereException(f'{x} and/or {y}
 ↪not odd')
```
It turns out that there's a package called pytest-cov on PyPI  
```
pytest --cov=mymul .
```
# Thinking Recursively in Python
![vc](https://files.realpython.com/media/Thinking-Recursively-in-Python_Watermarked.1825397c00ea.jpg)

Recursion can be defined as the process of defining something in terms of itself. In simple words, it is a process in which a function calls itself directly or indirectly.

The algorithm for iterative present delivery implemented in Python:
```
houses = ["Eric's house", "Kenny's house", "Kyle's house", "Stan's house"]

def deliver_presents_iteratively():
    for house in houses:
        print("Delivering presents to", house)
```
To demonstrate this structure, let’s write a recursive function for calculating n!:

1. Decompose the original problem into simpler instances of the same problem. This is the recursive case:

```
n! = n x (n−1) x (n−2) x (n−3) ⋅⋅⋅⋅ x 3 x 2 x 1
n! = n x (n−1)!
```

2. As the large problem is broken down into successively less complex ones.
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
![print](https://files.realpython.com/media/stack.9c4ba62929cf.gif)

# Maintaining State
So to maintain state during recursion you have to either:

* Thread the state through each recursive call
* Keep the state in global scope
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
![nn](https://robocrop.realpython.net/?url=https%3A//files.realpython.com/media/state_3.3e8a68c4fde5.png&w=1293&sig=365778ead2c38e2a10b95f53f3fc2f0f2e2bbce0)

# Recursive Data Structures in Python
is recursive if it can be deﬁned in terms of a smaller version of itself.
>A list is an example of a recursive data structure.
```
# Return a new list that is the result of
# adding element to the head (i.e. front) of input_list
def attach_head(element, input_list):
    return [element] + input_list
    attach_head(1,                                                  # Will return [1, 46, -31, "hello"]
            attach_head(46,                                     # Will return [46, -31, "hello"]
                        attach_head(-31,                        # Will return [-31, "hello"]
                                    attach_head("hello", [])))) # Will return ["hello"]
 
[1, 46, -31, 'hello']
```

![hello](https://files.realpython.com/media/list.3df62a89243d.gif)

# Naive Recursion is Naive
Fibonacci surmised that the number of pairs of 🐰 rabbits born in a given year is equal to the number of pairs of 🐰rabbits born in each of the two previous years, starting from one pair of rabbits in the ﬁrst year.
```
Fn = Fn-1 + Fn-2
The base cases are:

F0 = 0 and F1 = 1
```
recursive function for fibonacci number
```
def fibonacci_recursive(n):
    print("Calculating F", "(", n, ")", sep="", end=", ")

    # Base case
    if n == 0:
        return 0
    elif n == 1:
        return 1

    # Recursive case
    else:
        return fibonacci_recursive(n-1) + fibonacci_recursive(n-2)

```