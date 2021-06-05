# Expressions and operators
JavaScript's expressions and operators, including assignment, comparison, arithmetic, bitwise, logical, string, ternary and more.

# Operators
This section describes the operators and contains information about operator precedence.

* [Assignment operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators#assignment_operators)
* [Comparison operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators#comparison_operators)
* [Arithmetic operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators#arithmetic_operators)
* [Bitwise operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators#bitwise_operators)
* [Logical operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators#logical_operators)
* [String operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators#string_operators)
* [Conditional (ternary) operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators#conditional_ternary_operator)
* [Comma operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators#comma_operator)
* [Unary operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators#unary_operators)
* [Relational operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators#relational_operators)

JavaScript has both binary and unary operators, and one special ternary operator, the conditional operator. A binary operator requires two operands, one before the operator and one after the operator:
```
operand1 operator operand2
For example, 3+4 or x*y.
```
A unary operator requires a single operand, either before or after the operator:
```
operator operand
```
# Assignment operators
An assignment operator assigns a value to its left operand based on the value of its right operand. The simple assignment operator is equal (=), which assigns the value of its right operand to its left operand. That is, x = y assigns the value of y to x.

# Return value and chaining
```
const z = (x = y); // Or equivalently: const z = x = y;

console.log(z); // Log the return value of the assignment x = y.
console.log(x = y); // Or log the return value directly.
```
# Destructuring
The destructuring assignment syntax is a JavaScript expression that makes it possible to extract data from arrays or objects using a syntax that mirrors the construction of array and object literals.
```
var foo = ['one', 'two', 'three'];

// without destructuring
var one   = foo[0];
var two   = foo[1];
var three = foo[2];

// with destructuring
var [one, two, three] = foo;
```
# Arithmetic operators
An arithmetic operator takes numerical values (either literals or variables) as their operands and returns a single numerical value. The standard arithmetic operators are addition (+), subtraction (-), multiplication (*), and division (/), note that division by zero produces Infinity). For example:
```
1 / 2; // 0.5
1 / 2 == 1.0 / 2.0; // this is true
```
# Bitwise operators
A bitwise operator treats their operands as a set of 32 bits (zeros and ones), rather than as decimal, hexadecimal, or octal numbers.

# String operators
In addition to the comparison operators, which can be used on string values, the concatenation operator (+) concatenates two string values together, returning another string that is the union of the two operand strings.
```
For example,
console.log('my ' + 'string'); // console logs the string "my string".
The shorthand assignment operator += can also be used to concatenate strings.
```
```
For example,

var mystring = 'alpha';
mystring += 'bet'; // evaluates to "alphabet" and assigns this value to mystring.
```
# Comma operator
The comma operator (,) evaluates both of its operands and returns the value of the last operand.
 The code prints the values of the diagonal elements in the array:
 ```

var x = [0,1,2,3,4,5,6,7,8,9]
var a = [x, x, x, x, x];

for (var i = 0, j = 9; i <= j; i++, j--)
//                                ^
  console.log('a[' + i + '][' + j + ']= ' + a[i][j]);
  ```
# Unary operators
A unary operation is an operation with only one operand.

# delete
The delete operator deletes an object's property. The syntax is:
```
delete object.property;
delete object[propertyKey];
delete objectName[index];
delete property; // legal only within a with statement
```
# typeof
The typeof operator is used in either of the following ways:
```
typeof operand
typeof (operand)
```
The typeof operator returns a string indicating the type of the unevaluated operand. operand is the string, variable, keyword, or object for which the type is to be returned. The parentheses are optional.

Suppose you define the following variables:
```
var myFun = new Function('5 + 2');
var shape = 'round';
var size = 1;
var foo = ['Apple', 'Mango', 'Orange'];
var today = new Date();
```
# Relational operators
A relational operator compares its operands and returns a Boolean value based on whether the comparison is true.

# in
The in operator returns true if the specified property is in the specified object. The syntax is:
```
propNameOrNumber in objectName
```

where propNameOrNumber is a string, numeric, or symbol expression representing a property name or array index, and objectName is the name of an object.

The following examples show some uses of the in operator.
```
// Arrays
var trees = ['redwood', 'bay', 'cedar', 'oak', 'maple'];
0 in trees;        // returns true
3 in trees;        // returns true
6 in trees;        // returns false
'bay' in trees;    // returns false (you must specify the index number,
                   // not the value at that index)
'length' in trees; // returns true (length is an Array property)

// built-in objects
'PI' in Math;          // returns true
var myString = new String('coral');
'length' in myString;  // returns true

// Custom objects
var mycar = { make: 'Honda', model: 'Accord', year: 1998 };
'make' in mycar;  // returns true
'model' in mycar; // returns true
```
# Primary expressions
Basic keywords and general expressions in JavaScript.

# this
Use the this keyword to refer to the current object. In general, this refers to the calling object in a method. Use this either with the dot or the bracket notation:
```
this['propertyName']
this.propertyName
```
# Grouping operator
The grouping operator ( ) controls the precedence of evaluation in expressions. For example, you can override multiplication and division first, then addition and subtraction to evaluate addition first.
```
var a = 1;
var b = 2;
var c = 3;

// default precedence
a + b * c     // 7
// evaluated by default like this
a + (b * c)   // 7

// now overriding precedence
// addition before multiplication
(a + b) * c   // 9

// which is equivalent to
a * c + b * c // 9
```
# Left-hand-side expressions
Left values are the destination of an assignment.

new
You can use the new operator to create an instance of a user-defined object type or of one of the built-in object types. Use new as follows:
```
var objectName = new objectType([param1, param2, ..., paramN])
```
# Loops and iteration
Loops offer a quick and easy way to do something repeatedly. This chapter of the JavaScript Guide introduces the different iteration statements available to JavaScript
```
for (let step = 0; step < 5; step++) {
  // Runs 5 times, with values of step 0 through 4.
  console.log('Walking east one step');
}
```
# for statement
A for loop repeats until a specified condition evaluates to false. The JavaScript for loop is similar to the Java and C for loop.

A for statement looks as follows:
```
for ([initialExpression]; [conditionExpression]; [incrementExpression])
  statement
```
# do...while statement
The do...while statement repeats until a specified condition evaluates to false.

A do...while statement looks as follows:
```
do
  statement
while (condition);
```
# while statement
A while statement executes its statements as long as a specified condition evaluates to true. A while statement looks as follows:
```
while (condition)
  statement
```
# labeled statement
A label provides a statement with an identifier that lets you refer to it elsewhere in your program. The syntax of the labeled statement looks like the following:
```
label :
   statement
```

# break statement
Use the break statement to terminate a loop, switch, or in conjunction with a labeled statement.The syntax of the break statement looks like this:
```
break;
break [label];
```
# for...in statement
The for...in statement iterates a specified variable over all the enumerable properties of an object. A for...in statement looks as follows:
```
for (variable in object)
  statement
```








