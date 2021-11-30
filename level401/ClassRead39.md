## React 3

Next.js: The React Framework
Next.js aims to have best-in-class developer experience and many built-in features, such as:

* An intuitive page-based routing system (with support for dynamic routes)
* Pre-rendering, both static generation (SSG) and server-side rendering (SSR) are supported on a per-page basis
* Automatic code splitting for faster page loads
* Client-side routing with optimized prefetching
* Built-in CSS and Sass support, and support for any CSS-in-JS library
* Development environment with Fast Refresh support
API routes to build API endpoints with Serverless Functions
* Fully extendable

## React context
React context is great when you are passing data that can be used in any component in your application.

These types of data include:

* Theme data (like dark or light mode)
* User data (the currently authenticated user)
* Location-specific data (like user language or locale)

## React context Aim to:
To avoid the problem of props drilling.
Props drilling is a term to describe when you pass props down multiple levels to a nested component, through components that don't need it.


How use React context
1. There are four steps to using React context:
2. Create context using the createContext method.
Take your created context and wrap the context provider around your component tree.
3. Put any value you like on your context provider using the value prop.
4. Read that value within any component by using the context consumer.

## useContext hook
Instead of using render props, we can pass the entire context object to ```React.useContext()``` to consume context at the top of our component.
