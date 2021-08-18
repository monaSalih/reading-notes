## The JavaScript Call Stack - What It Is and Why It's Necessary
What is a ‘call’?
✔ function invocation 
How many ‘calls’ can happen at once?
✔ single-threaded
What does LIFO mean?
✔ Last In, First Out (LIFO) principle to temporarily store and manage function invocation (call).

Draw an example of a call stack and the functions that would need to be invoked to generate that call stack?
1. When secondFunction() gets executed, an empty stack frame is created. It is the main (anonymous) entry point of the program.
2. secondFunction() then calls firstFunction()which is pushed into the stack.
3. firstFunction() returns and prints “Hello from firstFunction” to the console.
4. firstFunction() is pop off the stack.
5. The execution order then move to secondFunction().
6. secondFunction() returns and print “The end from secondFunction” to the console.
7. secondFunction() is pop off the stack, clearing the memory.

What causes a Stack Overflow?
✔ A stack overflow occurs when there is a recursive function (a function that calls itself) without an exit point. The browser (hosting environment) has a maximum stack call that it can accomodate before throwing a stack error 

## JavaScript error messages && debugging
What is a ‘refrence error’?
```
This is as simple as when you try to use a variable that is not yet declared you get this type os errors.
console.log(foo) // Uncaught ReferenceError: foo is not defined
```
What is a ‘syntax error’?
This occurs when you have something that cannot be parsed in terms of syntax, like when you try to parse an invalid object using JSON.parse.
```
JSON.parse( {'foo': 'bar'} ) // Uncaught SyntaxError: Unexpected token o in JSON at position 1
```
What is a ‘range error’?
Try to manipulate an object with some kind of length and give it an invalid length and this kind of errors will show up.
```
var foo= []
foo.length = foo.length -1 // Uncaught RangeError: Invalid array length
```
What is a ‘tyep error’?
His types of errors show up when the types (number, string and so on) you are trying to use or access are incompatible, like accessing a property in an undefined type of variable.
```
var foo = {}
foo.bar // undefined
foo.bar.baz // Uncaught TypeError: Cannot read property 'baz' of undefined
```
What is a breakpoint?
✔  it is easier to create a code execution in scenarios like this by taking into account the call stack which is available, for example, in chrome developer tools “sources” tab.

What does the word ‘debugger’ do in your code?
✔  Debugging is the process of detecting and removing of existing and potential errors (also called as ‘bugs’) in a software code that can cause it to behave unexpectedly or crash. To prevent incorrect operation of a software or system, debugging is used to find and resolve bugs or defects. 