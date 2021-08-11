# Thinking in React

* How would you break a mock into a component heirarchy?
it apply to components?
The mock looks like this:
![mock](https://reactjs.org/static/1071fbcc9eed01fddc115b41e193ec11/d4770/thinking-in-react-mock.png)

You shoud do:
✔  draw boxes around every component (and subcomponent) in the mock and give them all names.

![mockStep](https://reactjs.org/static/eb8bda25806a89ebdc838813bdfa3601/6b2ea/thinking-in-react-components.png)

following these five component italicized for data what each component represents.

1. FilterableProductTable (orange): contains the entirety of the example

2. SearchBar (blue): receives all user input

3. ProductTable (green): displays and filters the data collection based on user input

4. ProductCategoryRow (turquoise): displays a heading for each category

5. ProductRow (red): displays a row for each product

✔ then arrange identified component hierarchy:

  * FilterableProductTable

  *  SearchBar
  *  ProductTable
     * ProductCategoryRow
     * ProductRow



* What is the single responsibility principle and how does ?
✔ that is, a component should ideally only do one thing. If it ends up growing, it should be decomposed into smaller subcomponents.


* What does it mean to build a ‘static’ version of your application?
✔ To build a static version of your app that renders your data model, you’ll want to build components that reuse other components and pass data using props.

* Once you have a static application, what do you need to add?
 ✔ need to add value
 
 
* What are the three questions you can ask to determine if something is state?
1. Is it passed in from a parent via props? If so, it probably isn’t state.

2. Does it remain unchanged over time? If so, it probably isn’t state.

3. Can you compute it based on any other state or props in your component? If so, it isn’t state.

