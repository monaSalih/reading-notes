# In Tests We Trust — TDD with Python

TDD stand for:Test Driven Development "how you think and write"
 TDD recommends writing tests that would check the functionality of your code prior to your writing the actual code.
 ![tdd](https://cdn-media-1.freecodecamp.org/images/1*FZGakHQbCUMAyDinf-KBiw.png)

Unit tests and TDD?
It is a piece of a code that invokes another piece of code (unit) and checks if an output of that action is the same as the desired output.

for example they hired you to know user age base on his name so you can use as devloper API can identify user gender based on his\her name
```
requests.get('https://api.genderize.io/?name=ana')
```

# Baby Steps

* start write and think how we can return gender using function (method/class)
it should be like following when write name and the result should be user gender.

```
Input: Ana [name]
Output: female [gender]
```
## Let’s write 🎉

```
def test_should_return_female_when_the_name_is_from_female_gender():
    detector = GenderDetector()
    expected_gender = detector.run(‘Ana’)
    assert expected_gender == ‘female’
```
as you see above we should write what the result should be
```
should return female when the name is from a female.
```
* the test name should following the same of module name for eample
>module file =gender.py
>test file =test_gender.py

much beeter to sepreate module file from test file ,as following
```
mymodule/
 — module.py
 — another_folder/
 — — another_module.py
tests/
 — test_module.py
 — another_folder/
 — — test_another_module.py
```
## AAA  structure widely used
###  AAA: Arrange, Act and Assert.
![AAA](https://miro.medium.com/max/1400/1*jLgrNjNC4vglYJKsmpRqmQ.png)

1.  Arrange is all the inputs/data that you need in your test.

2. Act  Arrange is all the inputs/data that you need in your test.

3. Assert is the validation between what the act returned and what your test expected.


# The Cycle
is a software development process relying on software requirements being converted to test cases before software is fully developed, and tracking all software development by repeatedly testing the software against all test cases

![Cycle](https://miro.medium.com/max/1000/1*TkxJ53qusI4hstPahbFG0A.png)

1. Red means to write a test that fails.
2. Green means to make test pass or work.
3. Refactor means to polish the code by eliminating the replication.
4. Repeat the process until the project is complete.

based on our problem we need to write method to return write answe:
```
def run(self, name):
    return 'female'
```

## TDD is not about the money/tests

### TDD more care about our software well.

complet our code to test detect male gender based on name using test

![gen](https://miro.medium.com/max/875/1*gxEKnrQuS7CO3hONTD7_hg.png)

# What does the if __name__ == “__main__”: do?
![name/main](https://codefather.tech/wp-content/uploads/2021/04/if-name-main-in-python-840x480.png?ezimgfmt=ng%3Awebp%2Fngcb10%2Frs%3Adevice%2Frscb10-2)

* Python files are called modules and they are identified by the .py file extension. A module can define functions,classes, and variables.

* So when the interpreter runs a module, the __name__ variable will be set as  __main__ if the module that is being run is the main program.

* But if the code is importing the module from another module, then the __name__  variable will be set to that module’s name.

![modul](https://cdn.journaldev.com/wp-content/uploads/2017/07/Python-Modules.png)

module:are simply files with the “.py” extension containing Python code that can be imported inside another Python Program.Consider a module to be the same as a code library.A file containing a set of functions you want to include in your application.

### when excuete file we write following line command
```
python script.py
```
* the following code well defined but none of them runs
*  the following code well only run if module "script.py" entry point to your program.  
*  you can test whether your script is being run directly by testing __name__ variable.
* If script is getting imported by some other module at that time __name__ will be module name.

## Why Do we need it?
1. to run module standalone by the user
2. If you import this script as a module in another script, the __name__ is set to the name of the script/module.
3. to reusable modules or independently programs
4. we used if __name__ == “main”: if the file run directly and imported


# Recursion
![recur](https://cdn.programiz.com/cdn/farfuture/6i17bRQT6hWIqw9JE5rMMyW527g7It_68T7kSzpIplo/mtime:1591262415/sites/tutorial2program/files/python-recursion-function.png)

Recursion: function defined in terms of itself via self-referential expressions. This means that the function will continue to call itself and repeat its behavior until some condition is met to return a result
## A Mathematical Interpretation
### Problem 🛠
A code have to calculate the sum of first n natural numbers
```
approach(1) – Simply adding one by one

f(n) = 1 + 2 + 3 +……..+ n
```

>we use mathematical approach to representing approach(1)
```
approach(2) – Recursive adding 

f(n) = 1                  n=1

f(n) = n + f(n-1)    n>1
```
in approach(2) call f() inside other function
>pov:used it to solve problem in easiar way

## What is base condition in recursion? 
to solve bigger problem is break it on smaller problem
```
int fact(int n)
{
    if (n < = 1) // base case
        return 1;
    else    
        return n*fact(n-1);    
}
```

## How a particular problem is solved using recursion? 
1. break big problem to small problem
2. add them one by one base  conditions that stop the recursion.

## Why Stack Overflow error occurs in recursion? 
 will be raised whenever the interpreter or builtin module code determines that the C stack is at or nearing a limit of safety. StackOverflow is a sub-class of RecursionError, so any code that handles RecursionError will handle StackOverflow
 ```
int fact(int n)
{
    // wrong base case (it may cause
    // stack overflow).
    if (n == 100) 
        return 1;

    else
        return n*fact(n-1);
}
 ```

![sta](https://codefather.tech/wp-content/uploads/2021/05/create-stack-python-840x480.png?ezimgfmt=ng%3Awebp%2Fngcb10%2Frs%3Adevice%2Frscb10-1)

## What is the difference between direct and indirect recursion

Direct Recursion:
When in the body of a method there is a call to the same method, we say that the method is directly recursive. That means Direct recursion occurs when a method invokes itself.
```
// An example of direct recursion
void directRecFun()
{
    // Some code....

    directRecFun();

    // Some code...
}
```
Indirect Recursion
Indirect recursion occurs when a method invokes another method, eventually resulting in the original method being invoked again.
```
// An example of indirect recursion
void indirectRecFun1()
{
    // Some code...

    indirectRecFun2();

    // Some code...
}
void indirectRecFun2()
{
    // Some code...

    indirectRecFun1();

    // Some code...
}
```

## What is difference between tailed and non-tailed recursion? 
Tail recursive
is method has the recursive call as the last statement in the method.
A non-tail
is recursive method can be converted to a tail-recursive method by means of an "auxiliary" parameter used to form the result.

## Advantages of Python Recursion
1. Reduces unnecessary calling of function, thus reduces length of program.
2. Very flexible in data structure like stacks, queues, linked list and quick sort.
3. Big and complex iterative solutions are easy and simple with Python recursion.
4. Algorithms can be defined recursively making it much easier to visualize and prove.

## Disadvantages of Python Recursion
1. Slow.
2. Logical but difficult to trace and debug.
3. Requires extra storage space.
4. Recursive functions often throw a Stack Overflow Exception when processing or operations are too large.
