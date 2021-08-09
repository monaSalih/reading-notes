# React Docs - lists and keys

* What does .map() return?
return new array

* If I want to loop through an array and display each   value in JSX, how do I do that in React?
✔ You can build collections of elements and include them in JSX using curly braces {}.

Following example to loop on numbers and return them on li
```
const numbers = [1, 2, 3, 4, 5];
const listItems = numbers.map((number) =>
  <li>{number}</li>
);
```


* Each list item needs a unique __keys__.


* What is the purpose of a key?
✔ Keys help React identify which items have changed, are added, or are removed

## The Spread Operator

* What is the spread operator?
✔ allows an iterable to expand in places where 0+ arguments are expected. It is mostly used in the variable array where there is more than 1 values are expected

* List 4 things that the spread operator can do.

* Concatenating or combining arrays.
* Using Math functions.
* Using an array as arguments.
* Adding an item to a list.

* Give an example of using the spread operator to combine two arrays.
```
const arr1 = [1,2,3]
const arr2 = [4,5,6]
const arr3 = [...arr1, ...arr2] 

```

* Give an example of using the spread operator to add a new item to an array.
```
const zoo = ['🦊', '🐮'];
const birds = ['🐧', '🐦', '🐤'];

zoo.push(...birds);

console.log(zoo); // ['🦊', '🐮', '🐧', '🐦', '🐤']
```

* Give an example of using the spread operator to combine two objects into one.
```
const a = ['to', 'code'];
const b = ['learning', ...a, 'is', 'fun']; 
console.log(b); 
```


## Videos (How to Pass Functions Between Components)

* In the video, what is the first step that the developer does to pass functions between components?
✔ create the function wherever the state
 
* In your own words, what does the increment function do?
✔ to increases one for item each time function loop

* How can you pass a method from a parent component into a child component?
✔ using props

* How does the child component invoke a method that was passed to it from a parent component?

 ✔ using state


 # Things i want to learn about
 🐱‍💻 learn more about map method and forEach