# Control flow
### The control flow is the order in which the computer executes statements in a script. Executes code depending on whether the form is complete or not:

```
if (field==empty) {
    promptUser();
} else {
    submitForm();
}
```
For example, the above excerpt might be inside a function that runs when the user clicks the ** Submit ** button for the form. The function could also include a loop, which iterates through all of the fields in the form, checking each one in turn. Looking back at the code in the if and else sections, the lines promptUser and submitForm could also be calls to other functions in the script. As you can see, control structures can dictate complex flows of processing even with only a few lines of code.

# JavaScript Functions

>A JavaScript function is a block of code designed to perform a particular task.

>A JavaScript function is executed when "something" invokes it (calls it).

### EXAMPLE

```
function myFunction(p1, p2) {
  return p1 * p2;   // The function returns the product of p1 and p2
}

```

# JavaScript Function Syntax
A JavaScript function is defined with the function keyword, followed by a name, followed by parentheses ().
The code to be executed, by the function, is placed inside curly brackets: {}
```
function name(parameter1, parameter2, parameter3) {
  // code to be executed
}
```
# Function Invocation
The code inside the function will execute when "something" invokes (calls) the function:
* When an event occurs (when a user clicks a button)
* When it is invoked (called) from JavaScript code
* Automatically (self invoked)

# Function Return
When JavaScript reaches a return statement, the function will stop executing.
Functions often compute a return value. The return value is "returned" back to the "caller":
```
var x = myFunction(4, 3);   // Function is called, return value will end up in x

function myFunction(a, b) {
  return a * b;             // Function returns the product of a and b
}
```
# Why Functions?

You can reuse code: Define the code once, and use it many times.

### Example
Convert Fahrenheit to Celsius:
```
function toCelsius(fahrenheit) {
  return (5/9) * (fahrenheit-32);
}
document.getElementById("demo").innerHTML = toCelsius(77);
```
# The () Operator Invokes the Function

Accessing a function without () will return the function object instead of the function result.

### Example
```
function toCelsius(fahrenheit) {
  return (5/9) * (fahrenheit-32);
}
document.getElementById("demo").innerHTML = toCelsius;
```
# Functions Used as Variable Values
Functions can be used the same way as you use variables, in all types of formulas, assignments, and calculations.
```
Example
Instead of using a variable to store the return value of a function:

var x = toCelsius(77);
var text = "The temperature is " + x + " Celsius";
You can use the function directly, as a variable value:

var text = "The temperature is " + toCelsius(77) + " Celsius";
```

# Local Variables
Variables declared within a JavaScript function, become LOCAL to the function.
```
Example
// code here can NOT use carName

function myFunction() {
  var carName = "Volvo";
  // code here CAN use carName
}

// code here can NOT use carName
```
