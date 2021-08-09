# React: Component Lifecycle Events

![Lifecycle](https://miro.medium.com/max/2000/0*pqn5ljaOw4kWrUdF)

## What are component lifecycle events?

methods can be called during the lifecycle of a component, and they allow you to update the UI and application states.
![reactLFevent](https://miro.medium.com/max/2000/0*0saPKFiTUk6W3FYp)

## Mounting
is the process of outputting the virtual representation of a component into the final UI representation.

## Updating
Following event happen during update or state change:

**static getDerivedStateFromProps, shouldComponentUpdate, render,
getSnapshotBeforeUpdate, componentDidUpdate, UNSAFE_componentWillUpdate, UNSAFE_componentWillReceiveProps**

## Unmounting
The final phase of the lifecycle if called when a component is being removed from the DOM.

### constructor()
The constructor for a React component is called before it is mounted.If the component is a subclass you should call super(props), or the props will be undefined.

```
class FishTableRow extends React.Component {
constructor() {
super(props); //gives us access to props
//Don’t call this.setState() here
this.state = { //intitialize local state
showDescription: false
}; }
```

### static getDerivedStateFromProps()
This method exists for rare cases where the state relies on changes in props over time.

### render()
Render is the only required method in a class component. It will examine this.props and this.state when called. The render function should not modify the component state because it would cause a lot of bugs by changing the state every time it rerenders. 

```
ReactDOM.render(
<FishTable fishes= {fishData}/>,//set fishes document.getElementById(‘app’)
);
```
### componentDidMount()
This method is invoked immediately after a component is mounted. If you need to load anything using a network request or initialize the DOM, it should go here.
```
componentDidMount() {
console.log(‘got videos’);
this.getVideos(‘cats’);
}
getVideos(query) {
var options = {
key: this.props.YOUTUBE_API_KEY,
query: query
};
```


## Reading Question
*  Render will apply first

* Mounting is first thing will happen in the lifecycle of React 

* orgnize following method base on order that they happen
constructor

render

componentDidMount

React Updates

componentWillUnmount

* ComponentDidMount is This method is invoked immediately after a component is mounted.

## video Question 
* we can pass any data type

* Props VS State
Props: they prefer look to it as arguments to a function,
React components are functions which return JSX. Typically when you have a piece of code that you would like to reuse, you can place that code into a function and any dynamic values that code used before can be accepted as arguments.

State: is  a JavaScript object which contains data that influence how the component looks at a certain point in time.
Also what make the state different compared to props. State is just a snapshot of the app in a time.


* We change state inside application When re-render 

* we can Store using state counter app

## i want to learn more about react native 