# List Comprehensions

![pic](https://i.ytimg.com/vi/x4pZSpRFxeI/maxresdefault.jpg)

#### List comprehension:
is a powerful and concise method for creating lists in Python that becomes essential the more you work with lists, and lists of lists.
<!-- jrfejferjijfoejf -->

## Syntax
Based on the following example:

>my_new_list = [ expression for item in list ]

You can see from this example that three ingredients are necessary for a python list comprehension to work.

1. First is the expression we’d like to carry out. expression inside the square brackets.

2. Second is the object that the expression will work on. item inside the square brackets.

3. Finally, we need an iterable list of objects to build our new list from. 

```
> Notes 
* Elegant way to create and manage lists. 
* More compact way of creating lists. 
* More flexible than for loops

```

# Create a List with range():

### Example 1: Creating a list with list comprehensions:

In the following example, we’re using the range() method to generate a list of numbers. Python iterates(or loops) through each item in that range, and saves a copy of the item in a new list called digits:

```
# construct a basic list using range() and list comprehensions
# syntax
# [ expression for item in list ]
digits = [x for x in range(10)]

print(digits)
Output

[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
```

### Create a List Using Loops and List Comprehension in Python
* To better illustrate how a list comprehension can be used to write more efficient Python code, we’ll take a look at a side by side comparison:

* In the following example, you’ll see two different techniques for creating a Python list.

```
# create a list using a for loop
squares = []

for x in range(10):
    # raise x to the power of 2
    squares.append(x**2)

print(squares)
[0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
```

## Multiplying Parts of a List:

By taking advantage of list comprehensions, it’s possible to work on only part of a list. For instance, if you only wanted the even numbers in a given range, you could find them using a filter.

```
# create a list with list comprehensions
multiples_of_three = [ x*3 for x in range(10) ]

print(multiples_of_three)
Output

[0, 3, 6, 9, 12, 15, 18, 21, 24, 27]
```

## Show the first letter of each word using Python

So far we’ve seen examples of building a list of numbers in Python. Next, let’s try working with strings and the various ways list comprehensions can be used to elegantly handle a list of strings.
```
# a list of the names of popular authors
authors = ["Ernest Hemingway","Langston Hughes","Frank Herbert","Toni Morrison",
    "Emily Dickson","Stephen King"]

# create an acronym from the first letter of the author's names
letters = [ name[0] for name in authors ]
print(letters)
Output

['E', 'L', 'F', 'T', 'E', 'S']
```

## Lower/Upper case converter using Python

Making use of Python’s lower() and upper() methods, we’ll use list comprehension to achieve this common task.

```

lower_case = [ letter.lower() for letter in ['A','B','C'] ]
upper_case = [ letter.upper() for letter in ['a','b','c'] ]

print(lower_case, upper_case)
Output

['a', 'b', 'c'] ['A', 'B', 'C']
```

## Print numbers only from a given string

Taking advantage of Python’s isdigit() method, we can extract the phone number from the user data.

```
Example 7: Identify numbers in a string using the isdigit() method

# user data entered as name and phone number
user_data = "Elvis Presley 987-654-3210"
phone_number = [ x for x in user_data if x.isdigit()]

print(phone_number)
Output

['9', '8', '7', '6', '5', '4', '3', '2', '1', '0']
```
## Parsing a file using list comprehension

It’s also possible to read files in Python using list comprehension.

```
# open the file in read-only mode
file = open("dreams.txt", 'r')
poem = [ line for line in file ]

for line in poem:
    print(line)
Output

Hold fast to dreams

For if dreams die

Life is a broken-winged bird

That cannot fly.

-Langston Hughs
```


