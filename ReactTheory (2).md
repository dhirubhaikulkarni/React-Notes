## 1. What is React?

Ans: 
- Open source front-end JavaScript library
- Developed by Facebook in 2011 by Jordan Walke. It was initially deployed on Facebook's News Feed section in 2011 and later used in its products like WhatsApp & Instagram.
- Made open source in 2013
- It follows the component-based approach for building reusable UI components, especially for single page application. 
- Used for developing interactive view layer of web and mobile apps. 

### Features of React:
1. It uses the virtual DOM instead of the real DOM.
2. It uses server-side rendering.
3. It follows uni-directional data flow or data binding.
4. React Reconciliation: 
  - React Reconciliation is the process through which React updates the Browser DOM. 
  - It makes the DOM updates faster in React. 
  - It updates the virtual DOM first and then uses the diffing algorithm to make efficient and optimized updates in the Real DOM.


## 2. Advantages of using React.
Ans:
- __Use of Virtual DOM to improve efficiency:__ React uses virtual DOM to render the view. As the name suggests, virtual DOM is a virtual representation of the real DOM. Each time the data changes in a react app, a new virtual DOM gets created. Creating a virtual DOM is much faster than rendering the UI inside the browser. Therefore, with the use of virtual DOM, the efficiency of the app improves.
- __Gentle learning curve:__ React has a gentle learning curve when compared to frameworks like Angular.
- __SEO friendly:__ React allows developers to develop engaging user interfaces that can be easily navigated in various search engines. It also allows server-side rendering, which boosts the SEO of an app.
- __Reusable components:__ React uses component-based architecture for developing applications. Components are independent and reusable bits of code. These components can be shared across various applications having similar functionality. The re-use of components increases the pace of development.
- __Huge ecosystem of libraries to choose from:__ React provides you with the freedom to choose the tools, libraries, and architecture for developing an application based on your requirement.

## 3. What are the limitations of React?
- Three major drawbacks:
 1. Not a full-blown framework
 2. JSX can sometimes become messy.
 3. Unstructured

## 4. What are hooks in react?
In simple terms:
- Hooks are a new addition in React 16.8. 
- They are basically functions that let you use state and other React class based features without writing a class. 
- Because of hooks we can now avoid writing React class components.

### 1.  useState()
- The useState() is a built-in React Hook that allows you for having state variables in functional components. 
- It should be used when the DOM has something that is dynamically manipulating/controlling.

### 2. useEffect(() => {})
- The useEffect hook in React is like a handy tool for functional components. 
- It helps manage tasks that aren't directly related to showing stuff on the screen, like fetching data from the internet, retrieving data from API endpoints, or setting up timers. 
- It can be used to update components even after they've been shown, making your app more dynamic.

## 5. What are keys in react?

- A key is a special string attribute that needs to be included when using lists of elements.
- __Keys help react identify which elements were added, changed or removed.__
- Keys should be given to array elements for providing a unique identity for each element.
    Without keys, React does not understand the order or uniqueness of each element.
    With keys, React has an idea of which particular element was deleted, edited, and added.

## 6. What is JSX?
- JSX stands for JavaScript XML. It allows us to write HTML inside JavaScript and place them in the DOM without using functions like appendChild( ) or createElement( ).
- const element = createElement(type, props, ...children)
- JSX provides syntactic sugar for React.createElement( ) function.
- We can write react applications without JSX as well.

## 7. Differences between functional and class components?
- Before the introduction of Hooks in React, functional components were called stateless components and were behind class components on a feature basis. After the introduction of Hooks, functional components are equivalent to class components.
- __Declaration:__ 
Functional components are nothing but JavaScript functions and therefore can be declared using an arrow function or the function keyword:

Functional component:-
```js
  function card(props){
   return(
      <div className="main-container">
        <h2>Title of the card</h2>
      </div>
    )
   }
  const card = (props) =>{
    return(
      <div className="main-container">
        <h2>Title of the card</h2>
      </div>
    )
   }
```
Class component:
```js
 class Card extends React.Component{
  constructor(props){
     super(props);
   }
    render(){
      return(
        <div className="main-container">
          <h2>Title of the card</h2>
        </div>
      )
    }
   }
```

- Handling props: Props are handled pretty straight forward, however, in class components they are handled in a different way.

- Handling state

- Function Components
1) There is no render method used in functional components.
2) Functional components run from top to bottom and once the function is returned it can’t be kept alive
3) Constructors are not used

- Class Components
1) It must have the render() method returning JSX (which is syntactically similar to HTML)
2) The class component is instantiated and different life cycle method is kept alive and is run and invoked depending on the phase of the class component.
3) Constructor is used as it needs to store state.
4) Life Cycle method is:
    - A) Mounting - componentDidMount()
    - B) Updating - componentDidUpdate()
    - C) Unmount - componentWillUnmount()
    - D) Error Handling - componentWillUnmount()
5) There are three categories of lifecycle methods: mounting, updating, and unmounting.
      - A component “mounts” when it renders for the first time. This is when mounting lifecycle methods get called.
      - The first time that a component instance renders, it does not update. Starting with the second render, a component updates every time that it renders.
      - A component’s unmounting period occurs when the component is removed from the DOM. This could happen if the DOM is rerendered without the component, or if the user navigates to a different website or closes their web browser.


## 8. What is the virtual DOM? How does react use the virtual DOM to render the UI?



- As stated by the react team, virtual DOM is a concept where a virtual representation of the real DOM is kept inside the memory and is synced with the real DOM by a library such as ReactDOM.

### Why was virtual DOM introduced? 

DOM manipulation is an integral part of any web application, but DOM manipulation is quite slow when compared to other operations in JavaScript. The efficiency of the application gets affected when several DOM manipulations are being done. Most JavaScript frameworks update the entire DOM even when a small part of the DOM changes.

For example, consider a list that is being rendered inside the DOM. If one of the items in the list changes, the entire list gets rendered again instead of just rendering the item that was changed/updated. This is called inefficient updating.

To address the problem of inefficient updating, the react team introduced the concept of virtual DOM.

For every DOM object, there is a corresponding virtual DOM object(copy), which has the same properties. The main difference between the real DOM object and the virtual DOM object is that any changes in the virtual DOM object will not reflect on the screen directly. Consider a virtual DOM object as a blueprint of the real DOM object. Whenever a JSX element gets rendered, every virtual DOM object gets updated.

    **Note- One may think updating every virtual DOM object might be inefficient, but that’s not the case. Updating the virtual DOM is much faster than updating the real DOM since we are just updating the blueprint of the real DOM.

React uses two virtual DOMs to render the user interface. One of them is used to store the current state of the objects and the other to store the previous state of the objects. Whenever the virtual DOM gets updated, react compares the two virtual DOMs and gets to know about which virtual DOM objects were updated. After knowing which objects were updated, react renders only those objects inside the real DOM instead of rendering the complete real DOM. This way, with the use of virtual DOM, react solves the problem of inefficient updating.

- Disadvantages Of Virtual DOM
  - Higher Memory Usage Problems: The diffing algorithms used by the Virtual DOM need to continuously compare elements to determine which components need to be updated/changed.
  - Memory Overhead: This is because the Virtual DOM requires additional memory compared to directly manipulating the Browser DOM.
  - Initialization Overhead: This initialization process can be slightly slower compared to directly rendering elements to the Browser DOM.
  
## 9. What are the differences between controlled and uncontrolled components?

- Controlled and uncontrolled components are just different approaches to handling input from elements in react. 

- __Controlled component:__ In a controlled component, the value of the input element is controlled by React. We store the state of the input element inside the code, and by using event-based callbacks, any changes made to the input element will be reflected in the code as well. For example:

    When a user enters data inside the input element of a controlled component, onChange function gets triggered and inside the code, we check whether the value entered is valid or invalid. If the value is valid, we change the state and re-render the input element with the new value.

    Example of a controlled component:
```js
function FormValidation(props) {
let [inputValue, setInputValue] = useState("");
let updateInput = e => {
  setInputValue(e.target.value);
};
return (
  <div>
    <form>
      <input type="text" value={inputValue} onChange={updateInput} />
    </form>
  </div>
);
}

```

As one can see in the code above, the value of the input element is determined by the state of the inputValue variable. Any changes made to the input element is handled by the updateInput function.

- __Uncontrolled component:__ In an uncontrolled component, the value of the input element is handled by the DOM itself. Input elements inside uncontrolled components work just like normal HTML input form elements.

    The state of the input element is handled by the DOM. Whenever the value of the input element is changed, event-based callbacks are not called. Basically, react does not perform any action when there are changes made to the input element.

    Whenever use enters data inside the input field, the updated data is shown directly. To access the value of the input element, we can use ref.

    Example of an uncontrolled component:

```js
function FormValidation(props) {
let inputValue = React.createRef();
let handleSubmit = e => {
  alert(`Input value: ${inputValue.current.value}`);
  e.preventDefault();
};
return (
  <div>
    <form onSubmit={handleSubmit}>
      <input type="text" ref={inputValue} />
      <button type="submit">Submit</button>
    </form>
  </div>
);
}
```



As one can see in the code above, we are not using onChange function to govern the changes made to the input element. Instead, we are using ref to access the value of the input element. 

## 10. Props in react

- The props in React are the inputs to a component of React.
- They can be single-valued or objects
- Passing custom data to the React component.
- They are immutable

## 11. State in react

- Every component in react has a built-in state object, which contains all the property values that belong to that component.
- In other words, the state object controls the behaviour of a component. Any change in the property values of the state object leads to the re-rendering of the component.
- State is a JavaScript object used to represent the internal mutable data of a component.
- It is managed and controlled by the component itself.
- State is mutable, and you can modify it using the setState method provided by React.
- State is accessible only within the component where it is defined.

## 12. prop drilling in React?

- Passing data to deeple nested components in hierarchy can be referred to as prop drilling.

## 13. What are error boundaries?

Introduced in version 16 of React, Error boundaries provide a way for us to catch errors that occur in the render phase.

## 14. What are the rules that must be followed while using React Hooks?

There are 2 rules which must be followed while you code with Hooks:

1. React Hooks must be called only at the top level. It is not allowed to call them inside the nested functions, loops, or conditions.
2. It is allowed to call the Hooks only from the React Function Components.

## 15. What is the use of useEffect React Hooks?
- The useEffect React Hook is used for performing the side effects in functional components. With the help of useEffect, you will inform React that your component requires something to be done after rendering the component or after a state change

- Using this, we can perform various calculations such as data fetching, setting up document title, manipulating DOM directly, etc, that don’t target the output value. The useEffect hook will run by default after the first render and also after each update of the component. React will guarantee that the DOM will be updated by the time when the effect has run by it.


## 16. Explain Strict Mode in React

- StrictMode is a tool added in version 16.3 of React to highlight potential problems in an application. It performs additional checks on the application.

StrictMode currently helps with the following issues:

- Identifying components with unsafe lifecycle methods: 
    1. Certain lifecycle methods are unsafe to use in asynchronous react applications. With the use of third-party libraries, it becomes difficult to ensure that certain lifecycle methods are not used.
    2. StrictMode helps in providing us with a warning if any of the class components use an unsafe lifecycle method.
- Warning about the usage of legacy string API:
    1. If one is using an older version of React, callback ref is the recommended way to manage refs instead of using the string refs. StrictMode gives a warning if we are using string refs to manage refs.
- Warning about the usage of findDOMNode:
    1. Previously, findDOMNode( ) method was used to search the tree of a DOM node. This method is deprecated in React. Hence, the StrictMode gives us a warning about the usage of this method.
- Warning about the usage of legacy context API (because the API is error-prone).

## 17. Name a few techniques to optimize React app performance.
There are many ways through which one can optimize the performance of a React app, let’s have a look at some of them:

- Using useMemo( ) -
    - It is a React hook that is used for caching CPU-Expensive functions.
    - Sometimes in a React app, a CPU-Expensive function gets called repeatedly due to re-renders of a component, which can lead to slow rendering. useMemo( ) hook can be used to cache such functions. By using useMemo( ), the CPU-Expensive function gets called only when it is needed.
- Using React.PureComponent -
    - It is a base component class that checks the state and props of a component to know whether the component should be updated.
    - Instead of using the simple React.Component, we can use React.PureComponent to reduce the re-renders of a component unnecessarily.
- Maintaining State Colocation -
    - This is a process of moving the state as close to where you need it as possible.
    - Sometimes in React app, we have a lot of unnecessary states inside the parent component which makes the code less readable and harder to maintain. Not to forget, having many states inside a single component leads to unnecessary re-renders for the component.
    - It is better to shift states which are less valuable to the parent component, to a separate component.
- Lazy Loading -
    - It is a technique used to reduce the load time of a React app. Lazy loading helps reduce the risk of web app performances to a minimum

## 18. How to pass data from in react components
- Child Component to Parent Component (using callbacks)

    This one is a bit tricky. We follow the steps below:

    - Create a callback in the parent component which takes in the data needed as a parameter.
    - Pass this callback as a prop to the child component.
    - Send data from the child component using the callback.

## 19. What are Higher Order Components?

- Simply put, Higher-Order Component(HOC) is a function that takes in a component and returns a new component. 

    ### When do we need a Higher Order Component?

    - While developing React applications, we might develop components that are quite similar to each other with minute differences. 
    - In most cases, developing similar components might not be an issue but, while developing larger applications we need to keep our code DRY, therefore, we want an abstraction that allows us to define this logic in a single place and share it across components. 
    - HOC allows us to create that abstraction.

## 20. What are the different phases of the component lifecycle?

There are four different phases in the lifecycle of React component. They are:

1. __Initialization:__ During this phase, React component will prepare by setting up the default props and initial state for the upcoming tough journey.

2. __Mounting:__ Mounting refers to putting the elements into the browser DOM. Since React uses VirtualDOM, the entire browser DOM which has been currently rendered would not be refreshed. This phase includes the lifecycle methods componentWillMount and componentDidMount.

3. __Updating:__ In this phase, a component will be updated when there is a change in the state or props of a component. This phase will have lifecycle methods like componentWillUpdate, shouldComponentUpdate, render, and componentDidUpdate.

4. __Unmounting:__ In this last phase of the component lifecycle, the component will be removed from the DOM or will be unmounted from the browser DOM. This phase will have the lifecycle method named componentWillUnmount.


## 21. Explain about types of Hooks in React.

There are two types of Hooks in React. They are:

1. Built-in Hooks: The built-in Hooks are divided into 2 parts as given below:

    - Basic Hooks:
        1. useState(): This functional component is used to set and retrieve the state.
        2. useEffect(): It enables for performing the side effects in the functional components.
        3. useContext(): It is used for creating common data that is to be accessed by the components hierarchy without having to pass the props down to each level.
    - Additional Hooks:
        1. useReducer() : It is used when there is a complex state logic that is having several sub-values or when the upcoming state is dependent on the previous state. It will also enable you to optimization of component performance that will trigger deeper updates as it is permitted to pass the dispatch down instead of callbacks.
        2. useMemo() : This will be used for recomputing the memoized value when there is a change in one of the dependencies. This optimization will help for avoiding expensive calculations on each render.
        3. useCallback() : This is useful while passing callbacks into the optimized child components and depends on the equality of reference for the prevention of unneeded renders.
        4. useImperativeHandle():  It will enable modifying the instance that will be passed with the ref object.
        5. useDebugValue(): It is used for displaying a label for custom hooks in React DevTools.
        6. useRef() : It will permit creating a reference to the DOM element directly within the functional component.
        7. useLayoutEffect(): It is used for the reading layout from the DOM and re-rendering synchronously.
        8. useNavigate(): The useNavigate hook is used to programmatically navigate between routes.
        9. useForm():  It is commonly used in conjunction with form libraries like react-hook-form. 
        10. forwardRef(): It is a feature in React that allows a component to pass its ref to a child component. 

2. Custom Hooks: A custom Hook is basically a function of JavaScript. The Custom Hook working is similar to a regular function. The “use” at the beginning of the Custom Hook Name is required for React to understand that this is a custom Hook and also it will describe that this specific function follows the rules of Hooks. Moreover, developing custom Hooks will enable you for extracting component logic from within reusable functions.

## 22. How does the performance of using Hooks will differ in comparison with the classes?

React Hooks will avoid a lot of overheads such as the instance creation, binding of events, etc., that are present with classes.
    Hooks in React will result in smaller component trees since they will be avoiding the nesting that exists in HOCs (Higher Order Components) and will render props which result in less amount of work to be done by React

## 23. What is React Router?
- React Router refers to the standard library used for routing in React. It permits us for building a single-page web application in React with navigation without even refreshing the page when the user navigates.

The major components of React Router are given below:
  -  BrowserRouter: It is a router implementation that will make use of the HTML5 history API (pushState, popstate, and event replaceState) for keeping your UI to be in sync with the URL. It is the parent component useful in storing all other components.
  -  Routes: It is a newer component that has been introduced in the React v6 and an upgrade of the component.
  -  Route: It is considered to be a conditionally shown component and some UI will be rendered by this whenever there is a match between its path and the current URL.
  -  Link: It is useful in creating links to various routes and implementing navigation all over the application. It works similarly to the anchor tag in HTML


## 24. Disadvantages of React
- Difficult to integratewirh am MVC framework like Rails.
- It's a Library, Not a Framework. Like other Javascript libraries, React contains pre-written code.
- React uses JSX, a syntax extension to JavaScript.
- Lack of Updated Documentation- Its vast open-source community is always coming up with new tools and dependencies.


## 25. What is the purpose of render() in React.

Each React component must have a render() mandatorily. It returns a single React element which is the representation of the native DOM component. If more than one HTML element needs to be rendered, then they must be grouped together inside one enclosing tag such as <form>, <group>,<div> etc. This function must be kept pure i.e., it must return the same result each time it is invoked.

## 26. What are synthetic events in React?

Synthetic events are the objects which act as a cross-browser wrapper around the browser’s native event. They combine the behavior of different browsers into one API. This is done to make sure that the events show consistent properties across different browsers.

## 27. Explain Flux
- Flux is an architectural pattern which enforces the uni-directional data flow. It controls derived data and enables communication between multiple components using a central Store which has authority for all data. Any update in data throughout the application must occur here only. Flux provides stability to the application and reduces run-time errors.

## 28. Explain Redux

- Redux is one of the most trending libraries for front-end development in today’s marketplace. It is a predictable state container for JavaScript applications and is used for the entire applications state management. Applications developed with Redux are easy to test and can run in different environments showing consistent behavior.

## 29.  What are the three principles that Redux follows?

1. __Single source of truth:__ The state of the entire application is stored in an object/ state tree within a single store. The single state tree makes it easier to keep track of changes over time and debug or inspect the application.
2. __State is read-only:__ The only way to change the state is to trigger an action. An action is a plain JS object describing the change. Just like state is the minimal representation of data, the action is the minimal representation of the change to that data. 
3. __Changes are made with pure functions:__ In order to specify how the state tree is transformed by actions, you need pure functions. Pure functions are those whose return value depends solely on the values of their arguments.

4. __Benifits Of Redux__:
  - It provides centralized state management i.e. a single store for whole application
  - It optimizes performance as it prevents re-rendering of component
  - Makes the process of debugging easier
  - Since it offers persistent state management therfore storing data for long times become easier.


30. How do you handle data persistence in a React application?

In a React application, data persistence can be handled using a variety of methods, including:

- Local storage: This allows you to store key-value pairs in the browser’s local storage, which can be retrieved even after the user closes the browser or restarts their device.
- Cookies: Cookies are small pieces of data that are stored in the user’s browser and can be accessed by the website on subsequent visits.
- IndexedDB: It’s a low-level API for client-side storage of large amounts of structured data, including files/blobs.
- Web SQL Database: This is a deprecated technology for storing data in a client-side database using SQL.
- Server-side storage: You can also store data on a remote server using an API or a database such as MySQL, MongoDB, etc.
- Redux or Mobx: State management libraries like Redux or Mobx can be used to manage and persist application state across different components and sessions.

## 31. Explain the concept of a Pure Component in React.

- A “pure component” in React is a component that updates only when its properties or state have changed.

## 32. How do you handle optimization in a large React application?

- Use the React Developer Tools to identify and fix performance bottlenecks. The React Developer Tools allow you to track the performance of individual components and identify which components are causing the most re-renders.

- Use the shouldComponentUpdate lifecycle method to prevent unnecessary re-renders. This method allows you to control when a component should update based on its props and state.

- Use PureComponent and memo instead of Components. These are more efficient alternatives to React.Component that only re-render when props or state have changed.

- Use the useEffect hook to handle side effects. This hook allows you to run side effects, such as network requests, after a component has rendered.

- Use the useMemo hook to memoize expensive calculations. This hook allows you to cache the results of expensive calculations and only recalculate them when the inputs have changed.

- Lazy loading: Lazy loading is a technique where you only load the components that are needed for the current view. This can greatly improve the performance of your application.

- Code splitting: Code splitting is a technique where you split your application into smaller chunks of code that are loaded on demand. This can greatly improve the performance of your application.

- Optimize the loading time of your application by using techniques like code minification, compression, and caching.

It’s also important to keep in mind that performance optimization is an ongoing process and you should regularly check and optimize your application as it grows.


## 33. Debouncing in JavaScript.

1) Debouncing is a programming practice used to ensure that time-consuming tasks do not fire so often, that it stalls the performance of the web page. 
2) In other words, it limits the rate at which a function gets invoked.
3) Debouncing in JavaScript is a practice used to improve browser performance. 
4) There might be some functionality in a web page that requires time-consuming computations. 
5) If such a method is invoked frequently, it might greatly affect the performance of the browser, as JavaScript is a single-threaded language. 


## 34. Memoization in JavaScript. 

1) Memoization is a technique for speeding up applications by caching the results of expensive function calls and returning them when the same inputs are used again.
2) Importance of Memoization:
	 When a function is given in input, it performs the necessary computation and saves the result in a cache before returning the value. 	
	 If the same input is received again in the future, it will not be necessary to repeat the process.
	 It would simply return the cached answer from the memory. 
	 This will result in a large reduction in a code’s execution time.

## 35. Closures in JavaScript.

1) Before talking about closure, let’s take a quick look at the concept of lexical scope in JavaScript. 
2) Lexical scoping defines the scope of a variable by the position of that variable declared in the source code. 
3) A function scope’s ability to access variables from the parent scope is known as lexical scope.
4) Closure is the concept of function + lexical environment in which function it was created. 
5) so every function declared within another function then it has access to the scope chain of the outer function and the variables created within the scope of the outer function will not get destroyed.
6) EG:
function OuterFunction(outer_arg) {
 
    function innerFunction(inner_arg) {
        return outer_arg + inner_arg;
    }
    return innerFunction;
}
let get_func_inner = OuterFunction(5);
 
console.log(get_func_inner(4)); = 9
console.log(get_func_inner(3)); = 8


## 36. Currying in javascript.
1) currying is a functional programming technique that involves breaking down a function that takes multiple arguments into a series of functions that take one argument each
2) It helps us to create a higher-order function
3) It reduces the chances of error in our function by dividing it into multiple smaller functions that can handle one responsibility.
4) It is very useful in building modular and reusable code
5) It helps us to avoid passing the same variable multiple times
6) It makes the code more readable

## 37. Shallow Copy And Deep Copy of Object

- Shallow Copy: 
1) When a reference variable is copied into a new reference variable using the assignment operator, a shallow copy of the referenced object is created.
2) This means both the old and new reference variables point to the same object in memory.
3) EG:
let employee = {
    eid: "E102",
    ename: "Jack",
    eaddress: "New York",
    salary: 50000
}
 
console.log("Employee=> ", employee);
let newEmployee = employee;    // Shallow copy
console.log("New Employee=> ", newEmployee);
 
console.log("---------After modification----------");
newEmployee.ename = "Beck";
console.log("Employee=> ", employee);
console.log("New Employee=> ", newEmployee);


- Deep Copy:
1) Deep copy makes a copy of all the members of the old object, allocates a separate memory location for the new object, and then assigns the copied members to the new object.
2) To create a deep copy of an object in JavaScript we use JSON.parse() and JSON.stringify() methods.
3) EG:
let employee = {
    eid: "E102",
    ename: "Jack",
    eaddress: "New York",
    salary: 50000
}
console.log("=========Deep Copy========");
let newEmployee = JSON.parse(JSON.stringify(employee));
console.log("Employee=> ", employee);
console.log("New Employee=> ", newEmployee);
console.log("---------After modification---------");
newEmployee.ename = "Beck";
newEmployee.salary = 70000;
console.log("Employee=> ", employee);
console.log("New Employee=> ", newEmployee);


## 38. What is Recursion Function in JS.
1) It is a feature used in creating a function that keeps calling itself but with a smaller input every consecutive time until the code's desired result from the start is achieved.
2) EG:
let decrementCounter = (number) => {
        // Base case condition....
        if(number === 0) return ; 
        console.log(number);
        decrementCounter(number - 1);
    }
decrementCounter(5);

## 39. what is the difference between map and foreach
1) forEach: 
  -The forEach() method does not returns a  new array based on the given array.	
  -The forEach() method returns “undefined“.	
  -The forEach() method doesn’t return anything hence the method chaining technique cannot be applied here. 	
  -It is not executed for empty elements.
2) Map: 
  -The map() method returns an entirely new array.	
  -The map() method returns the newly created array according to the provided callback function.
  -With the map() method, we can chain other methods like, reduce(),sort() etc.
  -It does not change the original array.


## 40. What is call back function?

1) The callback is a function that is passed as a parameter to another function. And this function will be called inside the function.
2) A callback function, often referred to simply as a callback, is a function that is passed as an argument to another function, and it is intended to be "called back" or executed at some point during the execution of the outer function. 
3) Callbacks are commonly used in programming, especially in asynchronous and event-driven environments.

function doSomethingAsync(callback) {
  // Simulating an asynchronous operation, like fetching data from a server
  setTimeout(function() {
    console.log("Task completed!");
    // Calling the callback function
    callback();
  }, 1000);
}

function callbackFunction() {
  console.log("Callback function called!");
}

// Using doSomethingAsync with a callback
doSomethingAsync(callbackFunction);


## 41. What is Promises?
1) A promise is an object which is used to handle asynchronous operations. 
2) It is used to handle multiple asynchronous operations which may have a dependency on each other.
3) An asynchronous operation is an operation that is not executed immediately. It is executed after some time. 
4) For example, if you are making a request to the server to get some data, then it will take some time to get a response from the server. So, we need to wait for the response.
5) The useCallback Hook only runs when one of its dependencies update.
6) This can improve performance.
7) One reason to use useCallback is to prevent a component from re-rendering unless its props have changed.
8) any,all,race,finally
9) Syntax:
function myDisplayer(some) {
  document.getElementById("demo").innerHTML = some;
}

let myPromise = new Promise(function(myResolve, myReject) {
  let x = 0;

// The producing code (this may take some time)

  if (x == 0) {
    myResolve("OK");
  } else {
    myReject("Error");
  }
});

myPromise.then(
  function(value) {myDisplayer(value);},
  function(error) {myDisplayer(error);}
);

## 42. what is async await function in javascript?
1) The async keyword transforms a regular JavaScript function into an asynchronous function, causing it to return a Promise.
2) The await keyword is used inside an async function to pause its execution and wait for a Promise to resolve before continuing.

Async - 
1) Async simply allows us to write promises-based code as if it was synchronous and it checks that we are not breaking the execution thread.
2) Async functions will always return a value. 
3) It makes sure that a promise is returned and if it is not returned then JavaScript automatically wraps it in a promise which is resolved with its value.

Await - 
1) Await function is used to wait for the promise. It could be used within the async block only.
2) It makes the code wait until the promise returns a result.

## 43. What is CORS? 

- Cross-origin resource sharing (CORS) is a mechanism for integrating applications. 
- CORS defines a way for client web applications that are loaded in one domain to interact with resources in a different domain. 
- This is useful because complex applications often reference third-party APIs and resources in their client-side code. 
- CORS allows the client browser to check with the third-party servers if the request is authorized before any data transfers.
- For example, your application may use your browser to pull videos from a video platform API, use fonts from a public font library, or display weather data from a national weather database.
Example:
app.use(function (req, res, next) {
  res.header("Access-Control-Allow-Origin", "*");
  res.header("Access-Control-Allow-Methods", "GET, PUT, POST, DELETE");
  res.header(
    "Access-Control-Allow-Headers",
    "Origin, X-Requested-With, Content-Type, Accept, access_token"
  );
  next();
}); 

## 44. What is JavaScript?
- JavaScript is an interpreted language. This means that the source code is executed directly by an interpreter without the need for a separate compilation step.
- JavaScript is a high-level, versatile programming language primarily known for its role in web development. 
- It enables the creation of dynamic and interactive content on websites. 
- JavaScript is often used in conjunction with HTML and CSS to build modern web applications.
- JavaScript is mainly executed on the client side (in the user's web browser), allowing for the manipulation of the Document Object Model (DOM). 
- Libraries and Frameworks: There are numerous libraries and frameworks built on top of JavaScript, such as jQuery, React, Angular, and Vue.js, which facilitate the development of 	complex web applications by providing pre-built components and tools.
- Server-Side Development: it is also used for server-side development. Node.js is a runtime environment that allows developers to execute JavaScript on the server.

## 45.  What is the event loop in JavaScript?
- The event loop is a fundamental concept in JavaScript that enables asynchronous programming.
- setTimeout function is good expample.
- Asynchronous operations, such as I/O operations or events, are handled separately from the call stack
- The event loop in JavaScript allows it to behave asynchronously and carry out non-blocking I/O operations even though it’s a single-threaded language. 
- The event loop is responsible for executing code, collecting and processing events, and carrying out queued sub-tasks.

## 46.How does the localStorage differ from sessionStorage?
Ans:
1) localStorage:
  - This means that data stored in localStorage is accessible across all pages on the same domain.
  - The data stored in localStorage persists even when the browser is closed and reopened. It remains stored until explicitly cleared by the user or the web application.
  - This uses for authentication tokens, or any data that needs to be retained for a longer duration.
2) sessionStorage:
  - Each tab or window has its own separate sessionStorage.
  - The data stored in sessionStorage is only available for the duration of the page session. 
  - If the user closes the tab or window, the sessionStorage data is cleared.
  - This uses where you need short-lived data, such as storing data.

## 47. What is the difference between find(), map() and filter() methods in JavaScript ?
-  find() : returns the first items in an array that satisfies a condition
-  map() : returns an array with the same length
-  filter() : returns an array with less items than the original array (with specified condition)

## 48. What is the reduce methods in JavaScript ?
Ans:
  - The reduce() method executes a reducer function for array element.
  - The reduce() method returns a single value: the function's accumulated result.
  - The reduce() method does not execute the function for empty array elements.
  - The reduce() method does not change the original array.
Example:
	// Input array
	let arr = [10, 20, 30, 40, 50, 60];
	// Callback function for reduce method
	function sumofArray(sum, num) {
		return sum + num;
	}
	//Fucntion to execute reduce method 
	function myGeeks(item) {
		// Display output
		console.log(arr.reduce(sumofArray));
	}
	myGeeks();

## 49. What is prototype in JS.
JavaScript is a prototype based language, so, whenever we create a function using JavaScript, JavaScript engine adds a prototype property inside a function, Prototype property is basically an object (also known as Prototype object), where we can attach methods and properties in a prototype object, which enables all the other objects to inherit these methods and properties


## 50. What is Hoisting in JS - 
  - In JavaScript, hoisting refers to the built-in behavior of the language through which declarations of functions, variables, and classes are moved to the top of their scope – all before code execution. 
  - In turn, this allows us to use functions, variables, and classes before they are declared

## 51. What is Lazzy Loading. 
1) It is an optimization technique in React That allows you to split your application into different smaller bundles.
2) These bundles are loaded only when the user navigates to a part of application that requires them.
3) This approach significantly improves the initial time of react application, especiallyfor longer projects with many components.

Lazzy Function - means is does not load initially, it will only load when it got triggered.

Benifits - 
  1) Faster Initial Load Time - Reduce initial bundle size.
  2) Improved Performance - Reduce Memory usage and improving performance
  3) modularization - Making Code easier and maintainable and Update Individual components.

## 52. Context API and how it facilitates state management in React without using Redux
  1) Context API is used to pass global variables anywhere in the code. 
  2) It helps when there is a need for sharing state between a lot of nested components. 
  3) It is light in weight and easier to use, to create a context just need to call React.createContext(). 
  4) It eliminates the need to install other dependencies or third-party libraries like redux for state management. 
  5) It has two properties Provider and Consumer.

## 53. Explain the building blocks of React? 
1) Components: These are reusable blocks of code that return HTML.
2) JSX: It stands for JavaScript and XML and allows you to write HTML in React.
3) Props and State: props are like function parameters and State is similar to variables.
4) Context: This allows data to be passed through components as props in a hierarchy.
5) Virtual DOM: It is a lightweight copy of the actual DOM which makes DOM manipulation easier.


## 54.  Does React Hook work with static typing? 
- Static typing refers to the process of code check during the time of compilation for ensuring all variables will be statically typed. 
- React Hooks are functions that are designed to make sure about all attributes must be statically typed. 
- For enforcing stricter static typing within our code, we can make use of the React API with custom Hooks.

## 55. Unidirectional behavior in React and its impact on application architecture
- Unidirectional data flow is a core principle in React that greatly influences application architecture. 
- It refers to the idea that data flows in one direction within a React application, typically from parent components down to their child components. 
- This pattern is enforced by React's component-based architecture and its use of properties (props) and state.

- Component Composition - Unidirectional data flow encourages a hierarchical structure of components, where parent components pass data down to their child components via props

- State Management: In React, state is typically managed in a few top-level components (often referred to as container components), and then passed down to child components as props. 

- Performance Optimization: By minimizing the number of components that need to be re-rendered when data changes occur, unidirectional data flow can lead to performance optimizations. 

## 57. Comparing Pure Components and Higher Order Components (HOC) in React

- Pure Components: Pure Components are a built-in feature in React that are used to optimize rendering performance. They automatically implement a shouldComponentUpdate method that shallowly compares props and state, and only re-renders if changes are detected. They are useful for optimizing components that rely only on props and state for rendering.
- Pure Components: Pure Components are implemented as classes that extend React.PureComponent instead of React.Component. They automatically perform a shallow comparison of props and state to determine whether a re-render is necessary.

- Higher Order Components (HOCs): HOCs are a pattern in React where a component is wrapped with a function that returns a new component with enhanced behavior. HOCs are typically used for code reuse, abstraction of logic, and adding additional functionality to components. They allow for cross-cutting concerns like authentication, data fetching, or logging to be applied to multiple components.

- Higher Order Components (HOCs): HOCs are implemented as functions that take a component as input and return a new component with additional functionality. HOCs can be implemented using either function components with hooks or class components. They typically wrap the original component and pass down props or inject additional props or behavior.

## 58. Error Handling and Error Boundaries in React to gracefully handle runtime errors

- Error handling in React is crucial for maintaining a smooth user experience, especially when unexpected runtime errors occur. 
React provides a mechanism called "Error Boundaries" to gracefully handle errors that occur during rendering

- Error Boundaries are special React components that catch JavaScript errors anywhere in their child component tree, log those errors, and display a fallback UI instead of crashing the entire component tree.

## 59. Server-Side Rendering (SSR) and its benefits for performance and SEO in React applications

1) Server-Side Rendering (SSR) in React involves rendering React components on the server and sending the fully rendered HTML to the client, rather than sending just a JavaScript bundle that needs to be parsed and executed to render the page.
2) SSR offers several benefits for performance and search engine optimization (SEO) in React applications:

- Faster Initial Page Load:
With SSR, the server sends pre-rendered HTML to the client, reducing the time it takes for the initial page to load. Users see content sooner, even before JavaScript is downloaded and executed.

- Improved Perceived Performance:
Users perceive the application to be faster since they see content sooner. Even if JavaScript bundle loading and execution are delayed, the user can already interact with the content on the page.

## 60. Exploring the differences between useMemo and useCallback in React
Use Case:
- useMemo is for memoizing values, while useCallback is for memoizing functions.

Return Value:
- useMemo returns a memoized value, while useCallback returns a memoized function.

Dependencies:
- Both hooks accept an array of dependencies, but their effects differ: useMemo re-runs when any of its dependencies change, while useCallback recreates the function only when its dependencies change.

Optimization Scenario:
- useMemo is typically used to optimize expensive calculations or data transformations, while useCallback is used to optimize the creation of callback functions, especially in scenarios where they are passed as dependencies.


## 61. ES6 Concept
  - The let keyword
  - The const keyword
  - Arrow Functions
  - The ... (Spread) Operator
  - Map Objects
  - Set Objects
  - Classes
  - Promises

## 62. What is Throttling?
- Throttling is used to call a function after every millisecond or a particular interval of time only the first click is executed immediately.
- Without throttling, a function may be invoked rapidly, leading to performance issues, unnecessary resource consumption, and a potentially poor user experience.
- Example 

const updateThrottleText = throttle((text)=> let data = "Hello Dhiru")

function throttle(cb, delay = 1000) {
    let shouldWait = false
    let waitingArgs
    const timeoutFunc = () => {
        if (waitingArgs == null) {
            shouldWait = false
        } else {
            cb(...waitingArgs)
            waitingArgs = null
            setTimeout(timeoutFunc, delay)
        }
    }

    return (...args) => {
        if (shouldWait) {
            waitingArgs = args
            return
        }

        cb(...args)
        shouldWait = true
        setTimeout(timeoutFunc, delay)
    }
}


## 63. What is Polyfill?
  - Polyfill is a way of providing futuristic API not available in browser.
  - We might need to do the native prototype modifications, so that we can get a feature/API.
  - There might be situations when we have a method not supported for specific browsers, in such cases we can use polyfills.



#### ----------------------------------- NODE JS -----------------------------------

## 1. What Is Node JS?

  - Node.js is a cross-platform, open-source JavaScript runtime environment that can run on Windows, Linux, Unix, macOS, and more
  - Node JS is a fast JavaScript runtime environment that we use to build server-side applications 
  - Node.js enables the execution of JavaScript on the server, facilitating the development of scalable and high-performance network applications.

  1) Non-blocking I/O: Node.js uses an event-driven, non-blocking I/O model, which means that it can handle many simultaneous connections without blocking the execution of code.
  2) Asynchronous Programming: Node.js relies heavily on asynchronous programming, using callback functions and Promises to handle operations like file I/O, network requests, and database queries efficiently.

## 2. What is event driven model?

  1) An event-driven model is a programming paradigm in which the flow of the program is determined by events such as user actions (mouse clicks, keyboard inputs), sensor outputs, or messages from other programs or threads. 
  2) Instead of following a linear sequence of instructions, an event-driven program responds to events as they occur. 
  3) This paradigm is commonly used in graphical user interfaces (GUIs), web development, and systems that involve user interaction.

## 3. Why we use node js instead of c# and java

  - One of the main advantages of Node. js is its high performance due to its event-driven, non-blocking I/O architecture. 
  - It uses a single-threaded event loop that allows it to handle a large number of concurrent connections efficiently.

## 4. What kind of libraries we used in node js

  - 1) body-parser:
		- It processes incoming request bodies, making it easier to handle POST and PUT requests. 
		- By parsing the body of an HTTP request and attaching it to the req. body property, it simplifies data extraction and manipulation in server-side logic.
	- 2) CORS :
		- It is a mechanism by which a front-end client can make requests for resources to an external back-end server
	- 3) jwtwetocken:
		- It is used for stateless authentication mechanisms for users and providers, this means maintaining sessions on the client side instead of storing sessions 		on the server.
	- 4) axios:
		- Axios is able to determine whether the request is made to the browser or to NodeJS. 
		Once this is established, it then identifies the proper way to make the API requests and returns a transformed response back to the client that made the 		server request
	- 5) aws-sdk
		- The AWS SDK for JavaScript simpliﬁes use of AWS Services by providing a set of libraries that are consistent and familiar for JavaScript developers

## 5. How to manage session in node js application
  - The first step in implementing session management in Node. js applications is to install and configure the session middleware. 
  - There are several session middleware options available for Node. js, including express-session , cookie-session , and session-file-store 


## 6. Is Node.js single-threaded?
- Yes, Node.js is single-threaded by default. 
- However, it utilizes event-driven architecture and non-blocking I/O operations to handle multiple concurrent requests efficiently, enabling scalability and high performance in applications.

## 7.What is a module in Node.js?
- In Node.js Application, a Module can be considered as a block of code that provide a simple or complex functionality that can communicate with external application. 
- Modules can be organized in a single file or a collection of multiple files/folders. 
- Modules are useful because of their reusability and ability to reduce the complexity of code into smaller pieces. 
- Some examples of modules are. http, fs, os, path, etc.

## 8.What kind of API function is supported by Node.js?
- There are two types of API functions supported by Node.js:
  - Synchronous: These API functions are used for blocking code.
  - Asynchronous: These API functions are used for non-blocking code.


## 9.What is npm and its advantages?
- npm (Node Package Manager) is the default package manager for Node.js. 
- It allows developers to discover, share, and reuse code packages easily. 
- Its advantages include dependency management, version control, centralized repository, and seamless integration with Node.js projects.

## 10. What is control flow in Node.js?
- Control flow in Node.js refers to the sequence in which statements and functions are executed.
- It manages the order of execution, handling asynchronous operations, callbacks, and error handling to ensure smooth program flow.

## 11.What is the Event Loop?
- The event loop allows Node to perform non-blocking I/O operations despite the fact that JavaScript is single-threaded. 
- It is done by assigning operations to the operating system whenever and wherever possible. 
- Most operating systems are multi-threaded and hence can handle multiple operations executing in the background. 
- When one of these operations is completed, the kernel tells Node.js, and the respective callback assigned to that operation is added to the event queue which will eventually be executed.

6 Queues Are in event loop with priority.
- Timer Queue - 3rd
- I/O Queue - 4th
- Check Queue - 5th
- Close Queue - 6th
- nextTick Queue - 1st 
- Promise Queue - 2nd 

- Features
  - The event loop allows us to use callbacks and promises.
  - The event loop executes the tasks starting from the oldest first.


## 12.What are the main disadvantages of Node.js?
Here are some main disadvantages of Node.js listed below:
  - Single-threaded nature: May not fully utilize multi-core CPUs, limiting performance.
  - NoSQL preference: Relational databases like MySQL aren’t commonly used.
  - Rapid API changes: Frequent updates can introduce instability and compatibility issues.

## 13.What is event-driven programming in Node.js?
- Event-driven programming is used to synchronize the occurrence of multiple events and to make the program as simple as possible. The basic components of an Event-Driven Program are:
- A callback function ( called an event handler) is called when an event is triggered.
- An event loop that listens for event triggers and calls the corresponding event handler for that event.

## 14.What is buffer in Node.js?
- The Buffer class in Node.js is used to perform operations on raw binary data. 
- Generally, Buffer refers to the particular memory location in memory. 
- Buffer and array have some similarities, but the difference is array can be any type, and it can be resizable. 
- Buffers only deal with binary data, and it can not be resizable. 
- Each integer in a buffer represents a byte. console.log() function is used to print the Buffer instance.

## 15.What are streams in Node.js?
- Streams are a type of data-handling method and are used to read or write input into output sequentially. 
- Streams are used to handle reading/writing files or exchanging information in an efficient way. 
- The stream module provides an API for implementing the stream interface. 
- Examples of the stream object in Node.js can be a request to an HTTP server and process.stdout are both stream instances.

## 16.Explain crypto module in Node.js
- The crypto module is used for encrypting, decrypting, or hashing any type of data. 
- This encryption and decryption basically help to secure and add a layer of authentication to the data. 
- The main use case of the crypto module is to convert the plain readable text to an encrypted format and decrypt it when required.

## 17.What is body-parser in Node.js?
- Body-parser is the Node.js body-parsing middleware. 
- It is responsible for parsing the incoming request bodies in a middleware before you handle it. 
- It is an NPM module that processes data sent in HTTP requests.

## 18.What is a cluster in Node.js?
- Due to a single thread in node.js, it handles memory more efficiently because there are no multiple threads due to which no thread management is needed. 
- Now, to handle workload efficiently and to take advantage of computer multi-core systems, cluster modules are created that provide us the way to make child processes that run simultaneously with a single parent process.

## 19.How to handle environment variables in Node.js?
We use process.env to handle environment variables in Node.js. We can specify environment configurations as well as keys in the .env file. To access the variable in the application, we use the “process.env.VARIABLE_NAME” syntax. To use it we have to install the dotenv package using the below command:

npm install dotenv

## 20. How can we implement authentication and authorization in Node.js?
Authentication is the process of verifying a user’s identity while authorization is determining what actions can be performed. We use packages like Passport and JWT to implement authentication and authorization.

## 21. How to manage sessions in Node.js?
Session management can be done in node.js by using the express-session module. 
It helps in saving the data in the key-value form. In this module, the session data is not saved in the cookie itself, just the session ID.

## 22. What is Middleware in Node js.
- Middleware in NodeJS refers to a software design pattern where functions are invoked sequentially in a pipeline to handle requests and responses in web applications. 
- It acts as an intermediary layer between the client and the server, allowing for modularization of request processing logic and enabling cross-cutting concerns such as authentication, logging, error handling, and data transformation.

1) Middleware Functions
2) Express.js Middleware
3) Error Handling Middleware

## 23. What is API and Types of API?
- API which stands for Application Programming interface is an interface between different software so that they can interact with each other very smoothly. 
- API is used to access different software services, retrieve data, and automate processes across different industries.

- An application programming interface is software that allows two applications to talk to each other.
- Application programming interface helps in data monetization.

1) SOAP: 
- SOAP is the Simple Object Access Protocol, a messaging standard defined by the World Wide Web Consortium.
- SOAP uses an XML data format to declare its request and response messages, relying on XML Schema and other technologies to enforce the structure of its payloads.

2) REST API's:
- REST can use XML, but is equally at home with JSON, HTML, and even plain text. 
- REST is a set of best practices that can be more fluid.

3) Composite API's
- Composite APIs are a design approach to batch API requests sequentially into a single API call. 
- Rather than multiple round trips to a server, a client can make one API request with a chain of calls and receive one response.


Whenever an async task completes in libuv, at what point does Node decide to run the associated callback function on the call stack?

What about async methods like setTimeout and setInterval which also delay the execution of a callback function?

If two async tasks such as setTimeout and readFile complete at the same time, how does Node decide which callback function to run first on the call stack?

1) What is dependency injection
2) What is CURL
3) What is different between call back function and promises
4) Why we can not use html,text in node?
5) What are the different types of API in node js
6) States of promises.




  - Differnt Data types in mongoDB
    - Array
    - Bson
    - int32
    - int64
    - string
    - undefined
    - null
    - boolean


  - this keyword:-
    - In JavaScript, the this keyword refers to an object.
    - In an object method, this refers to the object.
    - Alone, this refers to the global object.
    - In a function, this refers to the global object.
    - In a function, in strict mode, this is undefined.
    - In an event, this refers to the element that received the event.
    - Methods like call(), apply(), and bind() can refer this to any object.

  - super keyboard
    - The super keyword is used to call the constructor of its parent class to access the parent's properties and methods.
    - As a function - super(arguments);
    - As an object - super.parentMethod(arguments);

  - Object Destructuring
    - The object destructuring assignments are JavaScript expressions that allow you to unpack and assign object properties into individual variables. 
    - The name of the individual variables can be the same as the object properties or different.
    - const { prop1, popr2 } = obj;

  - arrow functions And Normal Functions
    - Arrow functions are anonymous functions and normal functions are not anonymous functions
    - Lexically scoped and Functionally scoped
    - in Array functions Duplicate named parameters are not allowed but in Normal functions the are allowed duplicate named parameters

  - profiler
    - ReactJS Profilers is a tool for profiling the react components, It measures how many times the react Application is rendered and how much time the components take to be rendered. 
    - It helps to identify the parts of the application that are slow so that the developer can optimize it for better performance. 
    - It is lightweight and no third-party dependency is required.
    - Syntax
        <div className="App">
            <Profiler id="Name" onRender={callback}>
                <Form labelname="Name " />
            </Profiler>
        </div>
