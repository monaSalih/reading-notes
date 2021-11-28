# React 

## Variable declaration
```
let x = 0
```
## Constant declaration
ES6 introduced the const keyword, which cannot be redeclared or reassigned, but is not immutable.
```
const CONST_IDENTIFIER = 0
```

## Arrow functions
The arrow function expression syntax is a shorter way of creating a function expression. Arrow functions do not have their own this, do not have prototypes, cannot be used for constructors, and should not be used as object methods.
```
let func = (a) => {} // parentheses optional with one parameter
let func = (a, b, c) => {}
```

## Concatenation/string interpolation
```
let str = `Release Date: ${date}`
```
## Multi-line strings
Using template literal syntax, a JavaScript string can span multiple lines without the need for concatenation.
```
let str = `This text
            is on
            multiple lines`
```
## Implicit returns
The return keyword is implied and can be omitted if using arrow functions without a block body.
```
let func = (a, b, c) => a + b + c 
```
## Classes/constructor functions
```
class Func {
  constructor(a, b) {
    this.a = a
    this.b = b
  }

  getSum() {
    return this.a + this.b
  }
}

let x = new Func(3, 4)
```
## Inheritance
```
class Inheritance extends Func {
  constructor(a, b, c) {
    super(a, b)

    this.c = c
  }

  getProduct() {
    return this.a * this.b * this.c
  }
}

let y = new Inheritance(3, 4, 5)
```
## Modules - export/import
```
let func = (a) => a + a
let obj = {}
let x = 0

export {func, obj, x}
```
## Introducing JSX
React embraces the fact that rendering logic is inherently coupled with other UI logic: how events are handled, how the state changes over time, and how the data is prepared for display.
```
const name = 'Josh Perez';
const element = <h1>Hello, {name}</h1>;

ReactDOM.render(
  element,
  document.getElementById('root')
);
```
## Specifying Attributes with JSX
You may use quotes to specify string literals as attributes:
```
const element = <div tabIndex="0"></div>;
```
You may also use curly braces to embed a JavaScript expression in an attribute:
```
const element = <img src={user.avatarUrl}></img>;
```
## Components and Props
This function is a valid React component because it accepts a single “props” (which stands for properties) object argument with data and returns a React element. We call such components “function components” because they are literally JavaScript functions.
```
class Welcome extends React.Component {
  render() {
    return <h1>Hello, {this.props.name}</h1>;
  }
}
```
## Rendering a Component
```
function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}

const element = <Welcome name="Sara" />;
ReactDOM.render(
  element,
  document.getElementById('root')
);
```
