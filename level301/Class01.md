# Introduction to React and Components

## React Native (also known as RN)"
 is a popular JavaScript-based mobile app framework that allows you to build natively-rendered mobile apps for iOS and Android. The framework lets you create an application for various platforms by using the same codebase.

![reactNative](https://appdevshop.com/wp-content/uploads/2017/02/react_native_banner-min.png)

### Component-Based Architecture

 focuses on the decomposition of the design into individual functional or logical components that represent well-defined communication interfaces containing methods, events, and properties. 

 Component-oriented software design **VS** traditional object-oriented:

* Reduced time in market and the development cost by reusing existing components.

* Increased reliability with the reuse of the existing components.

### What is a Component?
A component is a software object, intended to interact with other components, encapsulating certain functionality or a set of functionalities. It has an obviously defined interface and conforms to a recommended behavior common to all components within an architecture.


#### A component can have three different views − object-oriented view, conventional view, and process-related view:
* Object-oriented view

A component is viewed as a set of one or more cooperating classes. Each problem domain class (analysis) and infrastructure class (design) are explained to identify all attributes and operations that apply to its implementation. 

* Conventional view

It is viewed as a functional element or a module of a program that integrates the processing logic.

* Process-related view

In this view, instead of creating each component from scratch, the system is building from existing components maintained in a library. such as:

1. A user interface (UI) component includes grids, buttons referred as controls, and utility components expose a specific subset of functions used in other components.
2. Other common types of components are those that are resource intensive, not frequently accessed, and must be activated using the just-in-time (JIT) approach.
3. Many components are invisible which are distributed in enterprise business applications and internet web applications such as Enterprise JavaBean (EJB), .NET components, and CORBA components.


### Characteristics of Components

* Reusability − Components are usually designed to be reused in different situations in different applications. However, some components may be designed for a specific task.

* Replaceable − Components may be freely substituted with other similar components.

* Not context specific − Components are designed to operate in different environments and contexts.

* Extensible − A component can be extended from existing components to provide new behavior.

* Encapsulated − A A component depicts the interfaces, which allow the caller to use its functionality, and do not expose details of the internal processes or any internal variables or state.

* Independent − Components are designed to have minimal dependencies on other components.


### Principles of Component−Based Design

The design of data structures, interfaces, and algorithms should conform to well-established guidelines to help us avoid the introduction of errors.

* The software system is decomposed into reusable, cohesive, and encapsulated component units.

* Each component has its own interface that specifies required ports and provided ports; each component hides its detailed implementation.

* A component should be extended without the need to make internal code or design modifications to the existing parts of the component.

* Depend on abstractions component do not depend on other concrete components, which increase difficulty in expendability.

* Connectors connected components, specifying and ruling the interaction among components. The interaction type is specified by the interfaces of the components.

* Components interaction can take the form of method invocations, asynchronous invocations, broadcasting, message driven interactions, data stream communications, and other protocol specific interactions.

* For a server class, specialized interfaces should be created to serve major categories of clients. Only those operations that are relevant to a particular category of clients should be specified in the interface.

* A component can extend to other components and still offer its own extension points. It is the concept of plug-in based architecture. This allows a plugin to offer another plugin API.

![principle](https://www.tutorialspoint.com/software_architecture_design/images/principles_of_component_based_design.jpg)


###  advantages of using component based architecture

* Ease of deployment − As new compatible versions become available, it is easier to replace existing versions with no impact on the other components or the system as a whole.

* Reduced cost − The use of third-party components allows you to spread the cost of development and maintenance.

* Ease of development − Components implement well-known interfaces to provide defined functionality, allowing development without impacting other parts of the system.

* Reusable − The use of reusable components means that they can be used to spread the development and maintenance cost across several applications or systems.

* Modification of technical complexity − A component modifies the complexity through the use of a component container and its services.

* Reliability − The overall system reliability increases since the reliability of each individual component enhances the reliability of the whole system via reuse.

* System maintenance and evolution − Easy to change and update the implementation without affecting the rest of the system.

* Independent − Independency and flexible connectivity of components. Independent development of components by different group in parallel. Productivity for the software development and future software development.


## Props
“Props” is a special keyword in React, which stands for properties and is being used for passing data from one component to another.
> But the important part here is that data with props are being passed in a uni-directional flow.


### Step by step tp learn how use Props in React 

1. define an attribute and its value(data)
2. Then pass it to child component(s) by using Props
3. render the Props Data

```
class ParentComponent extends Component {  
  render() {
    return (
      <h1>
        I'm the parent component.
        <ChildComponent />
        <ChildComponent />
        <ChildComponent />
      </h1>
    );
  }
}
```

### props flow:

uni-directional flow:(one way from parent to child)where it means the data passed from parent to child also props data is read-only, which means that data coming from the parent should not be changed by child components.

![flowProps](https://miro.medium.com/max/667/1*ucOxan56LKUm3gkjaePwRg.png)

## thing want to learn about 

to be more familiar when use react