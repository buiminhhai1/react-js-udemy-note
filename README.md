# react-js-udemy-note
deeper react js to get a job.
## Section 1 Introduction
### 1 What is react?  
What is React? "A JavaScript Library for buiding User Interfaces" 
  It is about building JavaScript-driven apps. React apps run in the browser. They don't run on the server, they run in the browser and this gives us a great advantage. Things happen instantly since they happen in the user's browser, We don't have to wait for a server response to get a new page or to render something new. "User Interfaces" are basically what the user sees and React is all about using components for building these. If you think about it, you can split up any web page into components
  React Components can be thought of as custom HTML elements. IN the end, you're just writing custom HTML elements. This is what React is about and it therefore solves the problem of having to build complex user interfaces with what HTML and JavaScript gives you; by writing maintainable, manageable and reusable pieces of that code which you can throw into your web pp wherever you need to use it
  ReactDOM is then about rendering these components to the real DOM. ReactDOM written like that with DOME all begin capital charaters which has a render method, this method allows us to render a JavaScript function as a component to real DOM and that treat it as a component part is exactly what React takes care about.
  I want to render a different component, a different person, I would have to hardcode the values into that and actually create a new component. The great thing about React and why components are so awesome and save us a lot of time is that we can configure them dynamically as we need them. So here what I'lll do is I'll actually add an argument to this person function which I'll name props, you can choose any name you want but the concept I'm using here is call props. React automatically gives me an argument in that function I turned into a component with this syntax down here with person.
  In very big applications, you can compose the entire application of reusable pieces and this component isn't even using any logic, it doesn't listen to clicks or stuff like that. In apps such as the app we build in this course, we will of course do that, we will append our own logic to our components and then we have small reusable, maintainable and easy to manage pieces with their own logic contained in them which we can use anywhere to build amazing applicatons.
  I'm calling ReactDOM render twice, these's nothing wrong with that but actually we can also do this a bit differently, we could have one div here in the HTML part which has an ID of app or root, doesn't matter, any ID of your choise

### 2. Why React?
  There are more reasons why we want to use React. React helps us with a  propblem we'll encounter with normal JavaScript;
 - the UI state becomes difficult to manage. In bigger JavaScript applications, you have to manually target elements in your DOM and if you then change the structure of you HTML code, chances are you will need to change the way of you targeted your elements because you used querySelector. Even if you use jQuery, traversing the DOM is easier, but it's still always something you have to keep in mind. If you've got more complex web apps where you dynamically add and remove elements, this quickly can become cumbersome. In our course project, we build an app which is highly dynamic where we are able to build a burger and dynamically add and remove ingredients. If you write this with normal JavaScipt code, it's going to be a nightmare. So React helps us by making the whole UI state management a non-issue. 
 - It allows us to focus on our business logic instead of keeping our application from exploding. Additionally, React is maintained by a big community. So chances are, the React code is written better than we could have ever written it. So therefore, it's highly-efficient and fast. The bigger your application gets, the more this matters too.
 - Finally, React features a huge ecosystem and an extremely-active immunity which means that there is a great chance that for a given problem you face, you'll find a solution or an extra package you can add to fix it..
 All these reasons why React is awesome and why you definitely consider it for your next project and why you made the right choise to start with this course.
 
 ### 6. React Alternatives.
 React Angular VueJS and not so much jQuery
 ## 7. Two Kinds of Applications
  When we talk about React, or also about Angular and Vue as a side note, we also have to keep in mind that we can essentially build two kinds of web applications with all these libraries and frameworks. 
  - Single page applications
  - Multi page Applications
  what's the different? 
  *Single page Applications* : 
  - we only get back one single HTML file from the server and we get back this file the first time user visits the page; so the first time the user visits example.com. Thereafter is managed with JavaScript; with React. The entire page consists of components which are rendered and handled by JavaScript.
  - So in sigle page applications, our page is built up with components and every component is a React components. The entire page is also managed by a root React component which is exclusively under React's control.
  - In the single-page-applications case, which is the case we'll cover in this course, we typically only have one ReactDOM.render call. You saw this method in the previous lectures where we created our first app.
   Now, we only need one ReactDOM.render call because we only have one root app component which is mounted to the DOM and which hosts all other React components. 
  *Multi Page Applications*: 
  - we get back multiple HTML pages where each page has the content for a given route a given URL we visited. For example.com and example.com/users, we get back two different pages. That's important. we might also use React, but only to create little widgets so to say; 
  individually-contained components we dump into that page but the 'entire page' is not managed by React. We also see this on some pages, but the more popular approach these days is to use the single page application approach, because if you manage the entire page with JavaScript, you never have to go back to the server and reload the page. This is an amazing user experience because everything happens instantly. Even if the user needs to wait, you're showing a spinner or you're still presenting a reactive web app;
  you're not just showing a loading page where the user can't do anything.
  - we also could split up our app into theoretical components, but actually a lot of the page is just going to be normal HTML and CSS code and some widgets we dump in. like an image gallery or something like that is managed by React.
  So, the entire page is not under React's control. The individual widgets don't know of each other's existence.
  - we would typically call ReactDOM.render more often to render our different components in different places of the app. You saw that ReactDOM.render allows you to pick a place in your HTML code where you want to render your app. Therefore, you have these widgets which don't know of each other's existence.
  
### 8. Course Outline
   1. Getting started -> 2. The Basics -> 3. Debugging -> 4. Styling components -> 5. Components Deep Dive -> 6. HTTP Requests -> 7. Routing -> 8. Validation -> 9. Redux -> 10. Authentication. -> 11. Testing introduction. -> 12. Deployment -> 13. Bonus(Animations, next step webpack)


## Section 2: Refresh Next Generation JavaScript 
### Export & Import
  JavaScript code you split up over multiple files. And obviously we already can split our code over multiple files. We just have to import them in the correct order in our html files. And the idea behind export and import statements and so-called modules is that inside of a JavaScript file, we can import content from another file so that the JavaScript files themselves know their dependencies.
  We export this the default keyword this is a special keyword marking this as the default export of this file and we can import this somewhere else and the import statement will shown in a second. We also might have a number of files where we export miltiple things, here a constant named clean which holds a function at the end and baseData which holds number in a third file. example 
```python
// file person.js
const person = {
  name: "Hai"
}
export default person;

// file utility.js 
export const clean = () => {...};
export const baseData = 10;

file app.js
import person from './person.js';
import psn from './person.js';
import {baseData} from './utility.js';
import {clean} from './utility.js';
```
### Understand classes
```python
  class Human {
    gender = 'male';
    
    printGender = () => console.log(this.gender);
  }
  class Pereson extends Human {
      name = "Hai"
    }
    printMyName = () => console.log(this.name); 
  }
  
  const person = new Person();
  person.printMyName(); // Hai
  person.printGender(); // male.
```
### Spread & Rest Operators.
  Let's now turn our heads towards new operators we'll be able to use in the future of JavaScript and we already can use today in our React project, the Spread and the Rest operators. Actually it's only one operator theree dots ... This may look strange but the operator is just three dots. Now if we call it spread o rest depends on where we use it, the spread operatoor is used to split up.
- Spread: Used to split up array elements OR object properties.
```python
const newArray = [...oldArray, 1, 2];
const newObject = {...oldObject, newProp: 5};
```
three dots in front of old array will simply pull out all the elements and add it to the new Array which we created with square brackets. it is the normal syntax the square brackets to create an array, the same for the object. We create a new object with curly braces with the new prop but then we also have ... olb object to pull out all the properties of the old object and their values and add them as key value pairs to the new object as a side note if the old object. So our own property takes precedence. This is the spread operator. 
- Rest operator: is the same operator but used differently here it's used to merge a list of function arguments into an array. We use it in a function argument list
```python
funcion sortArgs(...args){
  return args.sort();
}
```
### Destructuring.
```python
const numbers = [1,2,3];
[num1, num2] = numbers; // [num1, , num3] =numbers;
console.log(num1, num2);
```
### References and Primitive Type Refresher
  If you copy Primitive Type value is copy 
  IF you copy references type like array, object the value coppied is pointer, so you want to make real copy you have to create new object and copy properties to new object. Just like this
```python
const person = {
  name:"Hai"
};
const secondPerson = person;
person.name = "Ha";
console.log(secondPerson); // person have name Ha

// real copy
const thirdPerson = {
  ...pereson
};
person.name = "Hai";
console.log(thirdPerson); // person have name Hai
```
### Refresh Array functions. 
```python
const numbers = [1, 2, 3];
const doubleNumArray = numbersr.map((num) => {
  return numm * 2;
});

console.log(numbers); // 1, 2, 3
console.log(doubleeNumArray); // 2, 4, 6
```
### Wrap up

## Section 3: Understanding the Base Features & Systax.
### 1. Introduction
### 2. Build Workflow
Why? 
- Optimize Code
- Use Next-Gen JavaScript Features
- Be More Productive
How? 
- Use Dependency Management Tool npm or yarn
- Use Bundler Recommended Webpack
- Use Complier (Next-Gen JavaScript) Babel + Preset
- Use a Development Server
### 3. Using Create React App
### 4. Understanding the Folder Structure
### 5. Understanding Component Basics
### 6. Understanding JSX
### 7. JSX Restrictions:
 - JSX clearly looks like html and it should, it should allow us to write html code in out JavaScript files, still since it isn't a JavaScript file and since it is JavaScript, some words can't be used. _class_ for example, which we would use in normal html assign a css class can't be used because it's a reserved word in JavaScript, we already used it here by the way, to create a new class. This is why we have to use _className_.
  All these elements you can use here like <div> and <h1> are actually managed or provided by the React library, we are not using the real html tags, React is converting them behind the scenes and React defines the attributes in quotation marks I should say. We can define on all these elements and we don't have the class attribute as we have on the regular.
 - Another restriction we face is that when we return something, we actually can't do return more root element. So typically you nest everything in one single root element you return.
### 8. Creating a Functional Component
### *Summary: Components & JSX Cheat Sheet*
  Components are the _core building block of React apps_.
  Actually, React really is just a library for creating components in its core
  
  A typical React app therefore could be depicted as a component tree - having one root elemet ("App") and then an potentially infinite amount of nested child components.
  Each component need to return/ render some JSX code - it defines which HTML code React should render to real DOM in the end.
  
  JSX is not HMTL but it looks a lot like it. Differences can be seen when looking closely though (for example className in JSX vs class in "normal HTML"). JSX is just syntactic for JavaScript, allowing you write HTMLish code instead nested React.createElement(...) calls.
  When creating components, you have to choice between two different way:
  *Function components* (also referred to as "presentational", "dumb" or "stateless" components.
```python
const cmp () = > { return <div>Some JSX </div>};
```
  *class-based components* (also referred to as "containers", "smart" or "statefull" components) 
```python
class Cmp extends Component {
  render() {return <div>some JSX</div>;}
}
```
### 9.Working with Components and Re-Using them
### 10. Outputing Dynamic Content
### 11. Working with Props.
### 12. Understanding the Children Property
### 13. Understanding  & Using state
### Summary Props & state
  _props_ and _state_ are CORE concepts of React. Actually, only changes in props and /or state trigger React to re-render your components and potentially update the DOM in the browser (a detailed look at how React checks whether to really touch the real DOM is provided)
  
  Props allow you to pass data from a parent (wrapping) component to a child (embedded) component.
```python
// AllPosts Component:
const posts = () => {
  return (
    <div>
      <Post title="My first Post"/>
    </div>
  );
}
```
Here, _title_ is a custom property (prop) set up on the custom _Post_ component. We basically replicate the default HTML attribute behavior we already know (e.g <input type="text"> informs the browser about how to handle that input)
  Post Component:
```python
const post = (props) => {
  return (
    <div> 
      <h1>{props.title}</h1>
    </div>
  );
}
```
The _Post_ component receives the _props_ argument. You can of course name this argument whatever you want - it's your function definition, React doesn't care! But React will pass one argument to your component function => An object, which contains all properties you set up on _<Post .../>.
_{props.title}_ then dynamically outputs the _title_ property of the _props_ object - which is available since we set the _title_ property inside _AllPosts_ component.

  State whilst props allow you to pass data down the component tree (and hence trigger an UI update), state is used to change the component, well, state from within. Changes to state also trigger an UI update.
```python
// NewPost Component:
class NewPost extends Component {
  state = {
    counter: 1
  };
  
  render() {
    return (
      <div>{this.state.counter}</div>
    );
  }
}
```
  Here, the _NewPost_ component contains _state_. Only class-based components can define and use _state_. You can of course pass the _state_ down to functional components, but these can't directly edit it.
  _state_ simply is a property of the component class, you have to call it _state_ though - the name is not optional. You can then access it via _this.state_ in your class JSX code (which you return in the required render() method).
  Whenever _state_ changes, the component will re-render and reflect the new state. the difference to _props_ is, that this happens within one and the same component - you don't receive new data (props) from outside.
  
### 14. Handle Event with method
Don't add parentheses (), this would execute it immediately once react renders this to the DOM because you execute this function 
```python
<button onClick={this.switchNameHandler}>Switch Name</button>
```
### 15. To Which Events Can You Listen? 
Clipboard Events: 
- Event Names: 
```python
onCopy, onCut, onPaste
```
- Properties: 
```python
  DOMDataTransfer clipboardData
```
Composition Events
- Event names: 
```python
onCompositionEnd onCompositionStart onCompositionUpdate
```
- Properties:
```python
string data
```

Keyboard Events: 
- Event names: 
```python
onKeyDown onKeyPress onKeyUp
```
- Properties:
```python
boolean altKey
number charCode
boolean ctrlKey
boolean getModifierState(key)
string key
number keyCode
string locale
number location
boolean metaKey
boolean repeat
boolean shiftKey
number which
```
and so on you can find a list of supported events here: https://reactjs.org/docs/events.html#supported-events

### 16. Manipulating the State
change the state you have to use this.setState() :)) 
### 17. Using the useState() Hook for State Manipulating 
  useState is the most important React hook, useState is the hook that allows us to manage state in a functional component.
  useState returns an array with exactly two elelements and always two elements, that's important. The first element we get back will always be our current state. The second element in state will always be a function that allows us to update this state, such that React us aware of it and will re-render this component which is of course
  You don't have one big state object, though you could and you could manually merge it if you prefer that but instead, you have multiple separated state slices.
  This is the useState hook and this is a glimpse at React hooks in general and this is the most important React hook.
  To summaraize it, React hooks is all about these use something functions with useState being the most important, that allow you to add functionality to functional components, like here useState allows us to add state management to functional components 

### 18. Stateless and Stateful Components
State review: In a component, state is data we import - typically to show the user - that is subject to change. It could change because the database we're getting from may be updated, the user modified it - there are so many reasons that data change!
  Stateful and Stateless Components
 Stateful and stateless components have many different names: 
 - Container vs Presentational components
 - Smart vs Dumb compo nents.
 The literal difference is that one has state, and the other doesn't. That means the stateful components are keeping track of changing data, while stateless components print out what is given to the via props or they always render the same thing.
 
### 19. Passing Method References Between Components
You can pass methods also as props so that you can call a method which might change the state in another component which doesn't hae direct access to state and which shouldn't have direct access to the state.
It's a common pattern and it's important to know, you can pass down click handlers which allow you to change data in the parent compoent. Maybe we also want to pass a value to our function.

### 20. Adding two way Binding
onChange will be fired whenever the value in this input changes.

### 21. Adding Styling with Stylesheets 
 
## Section 5: Styling React Components & Elements
### 1. Outlining the Problem set
THe issue we cannot use pseudos selectors here. The advantage of course is the styling is only applied to this button and to no other button in the application if we had another button. And I already mentioned the alternative would be to style it in the css file and there we can use normal css including pseudo selectors like hove but this would then globally affect all buttons in our application, even if they were placed in other components
### 2. Setting Styles Names Dynamically
### 3. Setting className Dynamically
So I want to assign it here and classes like this won't work anymore because
### 4. Adding and Using Radium 
Radium is a popular package for react which allows us to use inline styles with pseudo selectors and media queries, so pretty awesome
```python
// have to import and wrap export 
import Radium from 'radium'
export default Radium(App);
```
### 5. Using Radium for Media Queries
```python
// import StyleRoot and wrap all element into <StyleRoot>
import Radium, {StyleRoot} from 'radium'
...
render(){
  return(
    <StyleRoot>
    ... some code here~
    </StyleRoot>
  );
}
```
### 6. Enable & Using CSS Modules
```python
// 1. You need to install dependency react-scripts
npm install react-scripts

// 2. You Have you to add and commit project if you control source with github and 
// You have to run 
npm run eject 
```
One important note If you're using git to track your changes make sure you add and commit all changes before you run the eject command, it will not work otherwise

## Section 5: Debugging React Apps: 
### Using Error Boundaries
  componentDidCatch, this is a method which receives potential error and some additional information passed into it automatically by React and componentDidCatch will be executed whenever a component we wrap with error boundary throws an error.
  Only use error boundaries for cases where you know that might fail and you can't control that.
  
## Section 7: Diving Deeper into Components and React Internals
### 4. Comparing Stateless and Statefull Components
### 5. Class-based vs Functional Components
Class-based: 
```python
class XY extends Component
Y. Access to State
Y. Lifecycle Hooks
Y. Access State and Props via "this"

Use if you need t omanage State for access to Lifecycle Hooks and you don't want to use React Hooks.
```

Functional components are way more powerful than they have beein in the past though and difference between class-based components and functional components therefore is way less strong than it used to be.
```python 
const XY = props => {...}
Y. Access to State
N. Lifecycle Hooks
Y. Access Props via "props"

Use in all Cases
```
### 6. Component Lifecycle
You will actually learn that functional components when using React hooks have equivalent   
Only available in Class-based Components!
```python
 constructor() 
 getDerivedStateFromProps();
 getSnapshotBeforeUpdate();
 componentDidCatch();
 componentillUnmount();
 shouldComponentUpdate();
 componentDidUpdate();
 componentDidMount();
 render();
``` 

#### Component Lifecycle - Creation
- constructor(props); Default ES6 class Feature, call super(props).
  Do: Set up State
  Don't: Cause Side- Effects
->>
- getDerivedStateFromProps(props,state); (rare) 
  Do: Sync state 
  Don't: Cause Side-Effects
->>
- render(): Prepare & structure your JSX Code
->>
- Render Child Components
->>
- componentDidMount(): You can definitely set up some code that executes in the future which update the state, for example when the respone from the server is back but don't do it right away when componentDidMount runs that you immediately call setState because that will trigger a re-render cycle and that is bad performance
  DO: Cause Side-Effects
  DON'T: Update state (trigger re-render)
  
### 7. Component Update Lifecycle (for props Changes)
  When props or state change which are the two triggers you have for a component to be re-evaluated.
- getDerivedStateFromProps(props,state): Not use to often, you would use it to initialize the state of a component that updates based on props you're getting. for example some form control which gets external properties and then you internally want to handle user input but initialize your state or update state based on outside changes. 
DO: Sync State to Props
DON'T: Cause side-effect
->>>
- shouldComponentUpdate(nextProps,nextState): this lifecycle method or hook here is interesting because it allow to cancel the updating process.
DO: Decide where to Continue or Not. Why woud you do that? For performance optimization. This should be used carefully because obviously, you can break your components if you block an update from happening incorrectly but it is very powerful since it allows you to also prevent unnecessary update cycles.
DON'T: Cause Side-Effects.
->>>
- render(): Prepare & Structure Your JSX Code.
->>>
- Update Child Component Props: Now React then goes ahead updates all child components of this component, so it evaluates all the child components you have in your JSX code of this main component we're looking at here for which this lifecycle here runs and of course every child component then also goes through that lifecycle if it receives new props or state 
->>>>
- getSnapshotBeforeUpdate(prevProps, prevState): this is a lifecycle hook that takes the previos props and the previos state as input and that actually return a snapshot object which you can freely configure and this also is a niche lifecycle hook which we'll not use to much.
DO: last-minute DOM ops 
DON"T: Cause Side-effects.
->>>>
- componentDidUpdate(): A lifecycle hook that signals that you are now done with the updating, that the render method has been executed and here you can now cause side effects, you could make an HTTP Request, though you'll have to watch out to not enter an infinite loop here. DON't Update State (triggers re-render) because that will sipmly lead to an unnecessary re-render cycle.
### 12. Using shouldComponentUpdate for Optimization: 
use shouldComponentUpdate super important help to save performance
### 13. Optimazing Functional Component with React.memo();
This basically uses memoization which is a technique where React will memoize, so basically store a snapshot of this component and only if its input changes, it will re-render it and otherwise if its inputs do not change and some parent component wants to update this cockpit component, React will give back that stored component.  

=====>>> Two methods above help us to Optimization Performance <<<=====
### 14. When should you optimize? 
You will have components that will basically always update when their parent updates.
If it is the cases where X components is certainly not interested in changes related to the Y component, then you should implement your check.
Otherwise if you're pretty sure that in all or almost all cases where your parent updates, you will need to update too, then you should not add shouldComponentUpdate or React.memo because you will just execute some extra logic that makes no sense and actually just slow down the application a tiny bit.

### 15. PureComponents instead of shouldComponentUpdate
If you implement a check where you simply want to compare all props that matter to a component for difference, then there is an easier way of writing that component.
  PureComponents are just a normal component that already implements shouldComponentUpdate with a complete props check, so that checks for any changes in any prop of that component.

### 16. How React Updates the real DOM.
(the DOM in the browser)
- 1 The render method being called does not immediately also render to the real DOM (Of course this also applies to functional components and the JSX returned there, NOT just to class-based components with render()!).
The name can be misleading, this does not mean that it renders it to the DOM. Render is more suggestion of what the HTML should look like in the end, but render can very well be called and lead to the same result as is already displayed and this is part of the reason why we use shouldComponentUpdate to prevent unnecessary render calls.
- 2 But even if we don't catch an unnecessary render call, maybe a prop did change and still we would render the same result for whatever reason, even then this does not mean that it immediately hits the real DOM and start re-rendering it, instead it first of all does something else, it compare virtual DOMs.
  It has an old virtual DOM and a re-rendered or a future virtual DOM. React takes this virtual DOM approach because it's faster than the real DOM. Now a virtual DOM simply is a DOM representation in JavaScript. You can of course represent all HTML and therefore DOM elements and objects in pure JavaScript, so without rendering anything to the browser and this is what happens here and React basically keeps two copies of the DOM (Old virtual DOM and Re-render virtual DOM). 
- 3 It has the old virtual DOM and then the re-rendered one, the re-rendered one is the one which gets created when render method is called. Now as I mentioned though, re-rendering or calling render doesn't immediately update the real DOM, instead React makes a comparison.
- 4 It compares the old virtual DOM to the new one and it checks if there are any differences. 
  If it can detect differences, it reaches out to the real DOM and updates it and even then, it doesn't re-render the real DOM entirely. For example if a button text changed, it will only update that text and not re-render the whole button, leave alone the whole DOM. 
  If no differences were found, then it doesn't touch the real DOM. Render did execute, the comparison was made and that is why shouldComponentUpdate might make sense to prevent this if it's not needed because this of course already also consts some resources but nonetheless the real DOM is never touched, you can rely on that.
- 5 The real DOM will only be touched if there are real differences and this of course is important because as you might know, accessing the DOM is real slow, this is something you want to do as little as possible and hence, React has this virtual DOM idea, compares the virtual DOM and make sure that the real DOM is only touched if needed.

This is what happens behind the scenes.
![alt text](https://github.com/buiminhhai1/react-js-udemy-note/blob/master/React%20Update%20to%20real%20DOM.PNG)

 ### 17. Rendering Adjacent JSX Elements
 The naming can be confusing but "Lifecycle Hooks" have absolutely _nothing to do_ with "ReacWt Hooks!"
props.children, children is special property that simply outputs whatever gets entered between the opening and closing tag of this component.

we'll use aux component as a wrapper in cases where I want to have adjacent elements without an extra DOM element being rendered to the real DOM
### 18. Using React.Fragment
Fragment does exactly the same thing as our aux component does. 
Therefore it's still nice to learn how this works under the hood.

### 19. Higher Order Components (HOC) - Introduction 
I mentioned that the aux component is a so-called higher order component which is why it's placed in the hoc forlder and it's named higher order component because all it does essentially is wraps another component, it does not contain its own logic, its own styling or add any structure to the JSX code or to the real DOM that will be rendered
Now let me repeat, this is just an example here, obviously there would be nothing wrong with sticking to a div but we'll introduce other higher order component throughout the course where we for example add error handing that we can wrap around any component that makes an HTTP request and all of a sudden, this becomes more useful.
The general concept is simply that you have a component that wraps other components that adds something to it, that could be styling, that could be additional HTML structure around it or that could also be some logic and we'll add that logic later once we added HTTP requests as I said, to automatically handle HTTP errors.

### 20. Anther Form of HOCs
- Function return a functional component.

- When you see them, remember what they do behind the scenes, they add something extra to the component. That could be HTML, some logic, CSS.

### 21. Passing unknown Props
where I also want to have a class around it, right? 
 
We actually do accept our props here and this will be the props of our wrapped component because we return this functional component in our higher order component, 
Now what doesn't work is that we set props equal to props because React automatically takes all the attributes you add to your JSX code and combines them in a props object. 
you can;t do that props={props}
So now props would not replace that props object but be added as a single property in the props passed to the wrapped component. 
But instead you can use another syntax where you use curly braces and then a feature called the spread operator where you spread the props you're getting. The props you're getting here in a Javascript object and the spread operator pulls out all the properites that are inside of this props object and distributes them as new key-value pairs on this wrapped component. 

### 22. Setting State Correctly 
regular components

What I want to show you now only matters for class-based components that use the state property and that therefore use set state to update their state. Now the good news is we're using setState correctly here, bad news is you can use it incorrectly but I will show you how and how to avoid it.

SO how could you use it in an invalid way? 

Let's say that whenever our name changes and we execute the nameChangeHandler, we want to count that, so we essentially count every keystroke made or everyt change made. 

SO in our nameChangeHandler, we would not just want to update persons but also some counter we keep track of. Now therefore we can of course add a counter to our state, here  
```python
//code here: 
this.setState({persons: persons, changeCounter: this.state.changeCounter + 1});
```
and yet it is the wrong way of update this. 
Behind the scenes, set state does not immediately trigger an update of the state of this component in a re-render cycle, instead it's basically scheduled by React and React will then perform the state update and re-render cycle when it has the available resources to do that, so when it basically decides that now is a good point of time to do that. 

Typically, that will of course be instantly especially in simple applications like this one but it's not guaranteed and I want you to memorize this because that is really important. 

You call setState synchoronously here but it's not guaranteed to execute and finish immediately and therefore, this state when used for a state update is not guaranteed to be latest state or the previos state on which you depend, it could be an older state.

Let's say you're also calling set state somewhere else in you application which happens almost simultaneously to this set state update and for some reason, this does not execute immediately and the other set state update finishes earlier some thing like this,

Then the state you depending on here might be an unexpected state, it might not be the previous state you would expect it to be and therefore there is a better way of update state when you are depending on the old state. Set state does not only take a JavaScript object, it also works when you pass in a function, so you can use either syntax.

Now when you're doing state updates that don't depend on the old state, there is nothing wrong with just passing the object, so without the change counter, this is perfect.
With the change counter however, you should use that optional syntax where you actually two arguments and I'm using an anonymous arrow function here, where the first arguement is your old state and I'll name it prev State for previous state 

### Typechecking With PropTypes
As your app grows, you can catch a lot of bugs with typechecking. For some applications, you can used javaScript extensions like Flow or TypeScript to typecheck your whole application. But even if you don't use those, React has some built-in typechecking abilities. To run typechecking on the props for a component, you can assign the special propTypes property:
```python
import PropTypes from 'prop-types';

class Greeting extends React.Component{
  render(){
    return (
      <h1>Hello, {this.props.name}</h1>
    );  
  }
}
Greeting.propTypes = {
    name: PropTypes.string
  }
  
export default Greeting;
```
PropTypes export a range of validators that can be used to make sure the data you receive is valid. In this example, we're using PropTypes.string. Whenn an invalid value is provided for a prop, a warning will be shown in the JavaScript console. For performance reasons, propTypes is only checked in development mode.
###### PropTypes:
Here is an example documenting the different validator provided: 
```python
import PropTypes from 'prop-types';
MyComponent.propTypes={
  // YOu can declare that a prop is a specific JS type. BY default, these are all optional
  optionalArray: PropTypes.array,
  optionalBool: PropTypes.bool,
  optionalFunc: PropTypes.func,
  optionalNumber: PropTypes.number,
  optionalObject: PropTypes.object,
  optionalString: PropTypes.string,
  optionalSymbol: PropTypes.symbol

}
```

### Using Refs
_Refs provide a way to access DOM nodes or React elements created in the render method._

In the typical React dataflow, _props_ are the only way that parent components interact with their children. 
To modify a child, you re-render it with new _props_.
However, there are a few cases when you need to imperatively modify a child outside of the typical dataflow. 
The child to be modified could be an instance of a React component, or it could be a DOM element. For both of theses cases, React provides an escape hatch.

#### When to Use Refs
Then are a few good use cases for refs: 
- Managing focus, text selection, or media playback.
- Trigger imperative animations.
- Integrating with third-party DOM libraries.

Advoid using refs for anything that can be done declaratively.
For example, instead of exposing open() and close() methods on a Dialog component, pass an isOpen prop to it.

#### Don't Overuse Refs:
Your first inclination may be to use refs to "Make things happen" in your app.
IF this is case, take a moment and think more critically about where state should be owned in the component hierarchy.
Often, it becomes clear that the proper place to "own" that state is at a higher level in the herarchy. 

### 28. Understanding Prop Chain Problem.
To conclude this module, we'll now dive into another exciting feature React offers you that can help you avoid overly long chains of passing props around.

Context was introduced by React and it helps us handle cases like this. where you need certain data, certain state in multiple components and you don't want to pass that state across multiple layers

### 29. Using Context API.
#### _Context provides a way to pass data through the component tree without having to pass props down manually at every level._
  In a typical React application, data is passed top-down (parent to child) via props, but this can be cumbersome for certain types of props (e.g locale preference, UI theme) that are required by many components within an application. 
 Context provides a way to share values like these between components with having to explicitly pass a prop through every level of the tree.
 Read a lot of information here https://reactjs.org/docs/context.html#api
#### When to Use Context 
  Context is designed to share data that can be considered "global" for a tree React components, such as the current authenticated user, theme, or preferred language.
  For example, in the code below we manually thread through a "theme" prop in order to style the Button component: 
```python
class App extends React.Component{
  render() {
    return <Toolbar theme="dark" />;
  }
}


const Toolbar = (props) => {
// The Toolbar component must take an extra "theme" prop
// and pass it to the ThemedButton. This can become painful
// if every single button in the app needs to know the theme
// because it would have to be passed through all components.
  return (
    <div>
      <ThemedButton theme={props.theme}/> 
    </div>
  );
}

class ThemedButton extends React.Component {
  render() {
    return <Button theme={this.props.theme}/>
  }
}
```
  Using context, we can avoid passing props through intermediate elements:
  
```python
// Context lets us pass a value deep into the component tree 
// without explicitly threading it through every component.
// Create a context for the current theme (with "light" as the default).

const ThemeContext = React.createContext('light');

class App extends React.Component{
  render(){
  // Use a Provider to pass the current theme to the tree below
  // Any component can read it, no matter how deep it is.
  // In this example, we're passing "dark" as the current value
    return (
      <ThemContext.Provider value="dark">
        <Toolbar /> 
      </ThemContext.Provider>
    );
  }
}

// A component in the middle doesn't have to pass the theme down explicitly anymore.
const Toolbar = (props) => {
  return (
    <div>
      <ThemedButton/>
    </div>
  );
}

class ThemedButton extends React.Component {
  // Assign a contextType to read the current theme context.
  // React will find the closest theme Provider above and use its value.
  // In this example, the current theme is "dark".
  static contextType = ThemeContext;
  render(){
    return <Button theme={this.context}/>;
  }
}
```
#### Before You Use Context
  Context is primaryly used when some data needs to be accessible by many components at different nesting levels. Apply it sparingly because it makes component reuse more difficult.

#### API
##### React.createContext
```python
const MyContext = React.createContext(defaultValue);
```
  Create a Context object. When React renders a component that subscribes to this Context it will read the current value from the closest matchhing _Provider_ above it in the tree.
  
  The _defaultValue_ argument is only used when a component does not have a matching Provider above it in the tree. This can be helpful for testing components in isolation without wrapping them.
  Note: passing undefined as a Provider value does not cause consuming component to use _defaultValue_ 

##### Context.Provider
```python
<MyContext.Provider value={/* some value */}>
```
  Every Context object comes with a Provider React component that allows consuming components to subscribe to context changes.
  Accepts a _value_ prop to be passed to consuming components that are descendants of this Provider. One Provider can be connected to many consumers. Providers can be nested to override values deeper within the tree. 
  All consumers that are descendants of a Provider will re-render whenever the Provider's value props changes. The propagation from Provider to its descendant consumers is not subject to the shouldComponentUpdate method, so the consumer is updated even when an ancestor component bails out of the update

##### Class.contextType
The contextType property on a class can be assigned a Contet object created by React.createContext(). This lets you consume the nearest current value of that Context type using this.context. You can reference this in any of the lifecycle methods including the render function.
```python
class MyClass extends React.Component{
  componentDidMount() {
    let value = this.context;
    /* perform a side-effect at mount using the value of MyContext */
  }
  
  componentDidUpdate() {
    let value = this.context;
    /* ... */
  }
  componentWillUnmount() {
    let value = this.context;
    /* ... */
  }
  render(){
    let value = this.context;
    /* render something based on the value of MyContext
    */
  }
}
```
##### Context.Consumer
```python
<MyContext.Consumer>
  {value=> /* render something based on the context value */}
</MyContext.Consumer>
```
  A React component that subscribes to context changes. This lets you subscribe to a context within a function component.
  Requires a function as a child. The function receives the current context value and returns a React node. The value argument passed to the function will be equal to the value prop of the closest Provider for this context above in the tree. If there is no Provider for this context above, the value argument will be equal to the defaultValue that was passed to createContext().

### Adding a Dynamic Ingredient Component
- use method Object.keys()
- [...Array()];
- reduce();

especially the burger ingredients. since it is a good practice in React to create granular components and not big chunks.
create a folder structure which is not only divided in components and containers but where inside the components and container, you also divide it up by feature area so that you quickly know okay if I need to work on the burger side,
prettye straightforward,

Now here's a thing we can do and we will actually do in the next lecture, we can add prop type validation

precise.
It has a keys method which extracts the keys of a given object and turns that into an array
You might not know it because you don't use it that often but you can create an array with it.  
It's these inner arrays which are interesting to us. What we can do is we can simply flatten this array to make sure we pull out the values of these inner array and trade one array only which contains all these values. 
We can do that by adding reduce to our ,,, logic here, reduce is a built-in array function.
 which allow us to transform an array into something else.
 It takes a function as an iput and this function receives two arguments passed in automatically by JavaScript, the previous value and the current value. The reduce method does not only accept these callback here. 
 It will then loop through all the elements and simply add them to the inital values by step.
 
### Adding the Build Controls 
Time to add some controls so that a user can actually control which ingredients a burger should have or should not have, and for that we need to add the build controls and we'll add this component in the  

### Displaying and updating the Burger Price

Here however we get it back with decimal numbers in javascript so we should fix this and maybe we also want to print that in well, emphasized.

### Adding the Order Button.

Im; analyzing of course my old state here. Now due to the way set state works, when we execute update purchase state, we might not get the updated ingredients and therefore, one we copy ingredients 
 y
### Creating a Responsive Sidedrawer
This is one clever way of adjusting this, setting the height as a property where we simply pass the percentage

### Reusing the Backdrop

### Improving Perfomance
shouldComponentUpdate checks might event hit the performance more tan doing an occasional unnecessary re-rendering.

I just want to highlight here that we're in the updating process. It doesn't have to be componentWillUpdate and we'll not use this hook here for anything important. SO definitely no need to implement componentWillUpdate here, componentDidUpdate will do and I simple want to console.log(orderSummar 


Alternatively of course, you could keep this as a functional component and wrap the exported component, so the Modal constant you're exporting with React.memo().

Now we're not doing that yet in the application, there is much initialization we have to do in our components.
other hooks like WillUpdate and so on which we don't use except for login here, well you typically don't use these that often. 
There might be some cases where you need to adjust your components state based on some props you received from outside.

## Section 9: Reaching out to the Web (Http/Ajax)
### 1. Introduction: or since we have that decoupling
### 2. Understanding HTTP request in React
The React app and the servers still need to communicate from time to time but they don't communicate by exchanging html pages.
So if a react app sends a request to a server, you don't get back a new html page instead you can back some json data typically or you send some json data to the server if you want to create some resources on the server for example:
  This is how that works, you have that decoupling and your server therefore typically is a RESTful API, just exposing some API endpoints to which you can send requests to get or send data from your standalone React application. 
  This is the approach I will show you in this modules and I will show you how to do that.
### 3. Understanding our Project and Introducing Axios
We need some way of sending these Ajax requests, and here you have basically two options,
JavaScript of course has the XMLHTTPRequest object, this object here.
With that you can construct your own Ajax requests and send them to specific URL and handle the repsonse.

Nothing wrong with that since React is just about writing JavaScript everywhere, you can of course use all the JavaScript features including XMLHttpRequest. But writing and configuring requests with that object manually is quite cumbersome,
### 4. Creating a HTTP Request to GET Data
Axios making HTTP request in React Applications,
Now where do we make this HTTTP request then? 
Let's have a look at the lifecycle sides again for that, maybe we find a fitting lifecycle hook there.
If we have a look at the lifecycle hooks we encountered during component creation, there is one life cycly hook we should you use for side effects, componentDidMount and the HTTP requests is a side effect, 
it doesn't affect you React logic or something like that but it has the side effect of fetching new data and if your React application is dynamically outputting some data which it probable is, the data changing of course is a side effect affecting your application.

So componentDidMount is a great place for causing side effects but not for updating state since it triggers a re-render.

We will still update thet state here once the HTTP request has gone and got us new data because we actually want to re-update the page, so here this is actually a wanted behavior. So componentDidMount is the best place to send a HTTP Request.

The thing of course is this should return some posts but trying to store them in a post constant won't work because of corse that get request happens ansynchronously, it doesn't finish immediately, it needs some time to go to the server and get the data.

JavaScript though executes your code in a synchronous manner, so after this line, the next line is executed immediately, it won't pause until this is finished, so it won't store the posts and the posts const here. 

This is the wanted behavior because we don't want to block the execution of our application just because we're waiting for this request to finish.

Axios therefore uses promises, a default JavaScript object introduced with ES6 and thanks to our workflow we're using with create react app also available in order browsers since the code gets complied to code which also works in olders browsers.

So Axios uses promises and GET returns a promise, so we can chain then on it, then is simply a method which takes a function as the input and this function will get executed once the promise resolves.

So once the data from the backend is there, we can say.
The function then receives a response object as input, this will be passed into the function automatically by axios and let's for now simply print that to the 
 we get a robust application with a reuseable higher order component which we can wrap around.
### Retrieving Data from from Backend.
however we'll also face another issue, the order summary will also use the ingredients and therefore fail.

so we're essentially wrapping the burger builder and that of course has one implication,

robust

The problem we have is if we add this higher order component, withErrorhandler to other components, we'll call componentWillMount again and again of course because the class component we return it is higher order component is created every time this is wrapped around an existing component, so every time we call withErrorHandler on the element we're exporting as we do in the burger builder. 

So we're actually attaching multiple interceptors in our application and we're attaching them to the sam axios instance. 

right now and we will face later in the course, the mentioned routing will lead to the problem.
once we have more pages where we might use withErrorHandler, we of course create this instance here multiple times, this component here and therefore all the old interceptors, so all interceptors we set up when we wrapped this around another component which might not be needed anymore still exist.

React to our requests and in the worst case, they lead to errors or do somehow change the state of our application.

But even in the best case, they leak memory because that's code that still runs that is not required anymore. 

So we should actually remove the interceptors when this component gets unmounted, so when this specific instance of our withErrorHandler wrapper is not needed anymore and there actually is a lifecycle hook for this too, it's componentWillUnmount. 

Now as the name suggests, this is a lifecycle method which is executed at the point of time a component isn't required anymore. 

## Section 11: Multi-Page-Feeling in a Single-Page-App: Routing
One important thing, routing, what this module is about is not built into the core of React. We'll use another package which is not created by Facebook but the defacto standard for this task

### Routing And SPAs 
Routing is about being able to show different pages to the user.
Most web applications you know probably have more than one page, They have a users page, they have a post's page, an account page whatever the page is about. 

Now of course you may wonder multiple pages in a single page application, how does that work together? 

Well keep in mind the idea behind a single page application is to have, well guess what?
A single page, a single html file. We still want to provide the user with a normal web using experience though, we want to show the user different pages for different URLs.

The trick just is that we don't actually have multiple html files, but then we instead use JavaScript to render different pages for different paths.
So we don't really have different files but simply we re-render parts off that single page or maybe the entire single page depending on which path the user navigated to in our application. 

This is what routing is about, parsing this path, so the path after our domain and showing the appropriate jsx or component code in our app. 
And for that as I said, we're going to use a router package to add such a functionality so that we don't have to parse that path on our own which is non-trivial. 
That router package has a couple of tasks, first of all of course it has to parse the URL path to understand where the user wanted to go to.

Then we as a developer have to configure different paths in our application which we support and the router package can then read our configuration basically, so that it knows which paths are supported and what should happen when the user visits one of these paths. 

This is the third step, it will then render or load the appropriate jsx or component code depending on which path the user visited. 

This is the idea behind routing, load different code, conditional JSX or component code for different paths and we use a router package so that we don't have to determine which path the user is on on our own.

You shouldn't really render a whole component's code here even though you could technically do that but that will mess up your code, will make it very hard to maintain but loading components like this here this is the default case which will use a lot.

This is rarely what you want in your React application, as long as the user is navigating around in it, you want to not reload the page, you want to just re-render the page in the page in the parts where it needs to be re-renderd to look like the new page.

So we need to change to behaviour so that we don't have a normal link here which reloads the page but that instead we prevent the rebuilding of the page and let React router only re-render parts of the DOM or tell React what to do re-render to be precise that needs to be re-rendered.

### Using Link to Switch Pages
### Using  Routing-Related Props
Right now in our application we are able to navigate around. We are able to do that without reloading the page.
Let's have a look at posts, there in componentDidMount which will be executed each time we changed a page because the component is really removed and added to the DOM all the time. 
### The "withRouter" HOC and Route Props
this utility information and regarding the history object, the utility methods even we can use to navigate around or find out where we are at.  

Now what if we actually want to get this information not in one of our containers, so not in a component which was loaded through a route as defined in the blog.js file but in a component which is rendered as part of such a container, like the POST's container. The post container is loaded with this route here in the Blog container and the post container container simply redners the post commponent then.

Now if we go into that Post component and for a sencond we turn this post component into a component
if we dare

then you will actually see that the props in the post components we see that four times because we're rendering four posts is just author, clicked, title 

There is no match, location, history prop in there as we have it in the posts component, plural, not the single

### Absolute vs Relative Paths
 By default, if you just enter to="/some-path" or to="some-path" that's an absolute path.
 Absolute path means that it's always appended right after your domain. Therefore, both syntaxes (with and without leading slash) lead to example.com/some-path.
 
 Relative Paths
 Sometimes, you might want to create a relative path instead. This is especially useful, if your component is already loaded given a specific path (e.g. posts) and you then want to append something to that existing path (so that you, for example, get /posts/new)
 
### Styling the Active Route
an anchor tag managed by the React router preventing the default which would be to really send that request.

NavLink It's pretty similar to link but it has some extra props which allow us to define some styling for the active link. 

By default react router treats these paths here as prefixes, and the same is true for links.

### Parsing Query Parameters & the Fragment
But how do you extract search (also rederred to as "query") params

### Understanding Nested Routes
We're not going to reach that route because we have the exact matching for just slash

Well it's our check in loadData, we're checking if our Id changed and we're checking for this,props.id  
Now just as everywhere else here, this needs to be this.props.match.params.id, this.props.id will never be set. 

### Redirecting Requests
So enough about route parameters and nested routes, let's talk about redirecting the user.
Sometimes you want to redirect the user, for example, let's say that you also want to lead the user to /posts, if he visits just slash. 

The redirect component as it is a component is simply used in your jsx code, there 
This is how we can redirect to ensure that the user is removed or is navigated to the route we want to have himm on. we can use,

### Conditional Redirects.
There, we probably want to redirect once we clicked submit button your and once we made our HTTP request. 
We often then want to change the page and not remain on that page. Using the redirect component 
so we have no chance of entering content
Therefore we need to render this conditionally and since it's a normal component as all of js React is, we just have to render it conditionally

Might feel strange at first that we render a component to leave the page but this is just how it works.

### Using the History Prop to Redirect
we can enter a new post and once this is done, we push a new page and we are redirected. Technically push pushes this page onto the stack, so if we click the back button,we go back to the new post page. 
Whereas redirect replaces current page so if we then click the back button and you can of course try this out after you comment this in again, if you click the back button after redirecting and not by pushing, 
alternative

### Working with Guards
Let's talk about something which is kind of related with redirecting, navigation guards. 
A guard is something you might know from other frameworks and their routers. Typically guards is for example used when you don't know whether the user is authenticated or not and there are some paths in your application, some routes you only want to allow the user to visit if he is authenticated. With the react router, you might need to have to think about these guards in a new way.
For example in the blog components here, in a blog container where we set up the routing for a new post and so on. 
Since in the end, all we're doing here is jus rendering some components, the route components, the switch component, if we want to make sure that new posts can't be reached, we can simple render this conditionally. 

### Handling the 404 Case (Unknown Routes)

### 242. Loading Routers Lazily
We're nearing the end, there's one more advanced concept though not difficult to implement but one advanced

concept I want to cover.

Let's go back to our application and to really show what I mean,

let me set auth to true so that we can go to new post again.

So now you see new post can be loaded,

and let's go to the network tab in the developer tools. There

if we have a look at all the requests once we load the page,

so if I go into posts you see that we're loading this bundle.js file

this contains all our source code,

in here, it's relatively big because we're in development mode,

it will be much smaller once you are shipping this for production,

It's optimized power build workflow automatically then, I'll talk about this later when we deploy

the app. Still loading the entire bundle with all the code of our application up front can be bad if we have

a big application with distinct features and distinct areas in the app where a user might never visit

a certain area. Like in our app, we have the posts,

if the user never visits new post, loading the code responsible for that component

doesn't make a lot of sense. If we have a look at our routes

I'm talking about the new post component here,

this should only be loaded if the user actually navigates to /newposts

otherwise new posts and all potential children are never needed.

So why should we download the code up front? Would it be better to not download it and hence have a smaller

upfront chunk to download and instead download the code responsible for this component and its children

when needed.

Now for a tiny application as ours here, this is not super useful because making that extra request for one kilobyte or something,

what this component is worth when it comes to its size,

that's not super useful but it is useful to know this technique for real for bigger applications you are building where this might matter where you are downloading quite a bit.

The technique of downloading only what you need is known as code splitting or lazy loading and there you would essentially want to make sure that in your component, you're only loading the component once you need it.

How does this work? To implement code splitting or lazy loading, we have create react app and react route for and that's important.

This technique will work for react router for and for create react app because code splitting depends heavily on the webpack configuration you are using, it is an advanced concept after all.

So the way I'm showing you is the way it works with the config from create react app which is a pretty modern and good configuration though, so chances are it also works in any decently set up webpack project or as I said at the beginning of this course,

I strongly recommend using create react app anyway.

So for this to work in this setup, we need a higher order component.

So let's create a new folder hoc and then there, I'll add a new component which I'll name AsyncComponent

AsyncComponent

.js

that's the javascript file name, because this component or this code here should help me load a component

asynchronously i.e. only when it's needed.

Now here in this AsyncComponent file I will create a new constant, a new function in here which I'll name

asyncComponent.

There I expect to get my import component argument which will in the end be a function and I'll come

back to how to use this asyncComponent function and what to pass here exactly over the next seconds.

So there, I now need to return something and I will return a class here which extends component,

so a normal react component

therefore I need to import react because it will also use some jsx and component from react. Now in

the body of that class here,

I now of course also need a render method.

But before we come to this, I'll set up state and there I want to have a state which with a component

property which is null. This state here, this component property will be set to the dynamically loaded

component and the code for this will get implemented in

componentDidMount.

So once this component was mounted here, this wrapping higher order component.

Now as I said import component should be a function reference in the end,

so what I want to do is I want to execute import component here and this actually will be a function

which will return as a promise.

I know because I know who I am how I'm going to use this AsyncComponent in the function of this.
dynamically.

So in this then blog, I can call this.setState and set my component state to cmp default. This is the

case due to be set up we're using here with create react app.

It is all of course heavily reliant on the type of function import component will refer to and which

I'll show you in the next minutes

as I said, no worries.

So now at some point of time, we will have loaded the actual component we want to use and it will be

stored in our state. Hence in the render method, we want to render it, I'll create a constant and name it C and

this should be this.state.component.

Then I want to return jsx in this render method and I'll check if C is set in a ternary expression.

If it is set, then I'll render C as a normal react component,

I'll use this this.props spread trick here to pass any props we might need to this component and I'll

set it to null if C is not set yet,

so if the component hasn't been resolved yet. Of course I now also need to export this asyncComponent

function here.

Now we can save this file and now we can go back to the blog component where we do import new posts,
 
I want to load this dynamically now.

Now the thing is when ever you are importing something like this here, with import something from somewhere

you basically inform webpack, the build tool which gets used behind the scenes about this dependency

and it will include it in the global bundle, this is its job.

Now for a lazy loading, this is exactly the opposite of what we want to do,

we don't want to include it in the bundle,

we want to load it when needed.

Still webpack needs to be able to dynamically prepare some extra bundle for this potentially loaded code.

So what we have to do is we have to comment out this old way of importing and instead I'll create a

new constant which I'll name AsyncNewPost, the name of course is up to you,

this will now use this new asyncComponent function we created in hoc folder.

So I'll import asyncComponent from.

And now I'll move up to the hoc folder and import it from that AsyncComponent file

and I'll then use AsyncComponent here and execute it.

Now asyncComponent this function, requires an argument and I told you that this argument, in that function

we named it import component, that this argument should be a function which is why we executed like one

here in componentDidMount

So we have to pass some function to asyncComponent and this should be an anonymous function,

I'm using an ES6 arrow function here.

The interesting part is what we return in this function

and keep in mind if you write it in one line, whatever comes right of the error is immediately returned.

If you use curly braces you need to return something with the return keyword

so I'm going to take the longer approach.

there I'll use the import keyword as a function.

This is a special syntax, the dynamic import syntax which means whatever comes between the parentheses here is only imported when that function here is executed and that function here will only be executed once we render AsyncNewPost to the screen.

So here, I then take my original path to new post and now I'm only importing this when this constant gets used somewhere.

Now of course I want to use it somewhere, I want to use it down at the bottom of my blog container at the new post route, instead of using new

post as a component,

I want to use AsyncNewPost as a component.

Eventually this will be a component because keep in mind AsyncComponent returns a component, we have a higher order component.

It returns a class with a render method so this is a valid component.

This component will eventually render some dynamically loaded component and we decide which component it should be with the function we passed to AsyncComponent.

Now if we save this and we go back to our application, watch that path on the bottom right

when I click on new post. Once I click there you'll see that this 1chunk.js file was

loaded which is very small.

This is an extra bundle webpack created because whilst bundling our code, it detected this dynamic syntax

here which it knows due to our set up we're using too, this build workflow setup and therefore it created the

extra bundle with the new post component and all potential child components that were exclusive to that

component if any.

But it didn't add it to the main bundle,

instead it's prepared to load it when needed

when we actually include AsyncNewPost which we only do when navigating to /newpost. This is how

### Lazy Loading With React suspense:

Now we had a look at lazy loading in this component and lazy loading like this still works and is perfectly fine if you are using re-act 60 not six and you can check doesn't the package adjacent file and I have a new demo project here by the way which you find attached to this lecture which you should download extract NPM install and then NPM start.

So if you are using the latest re-act word in here or re-act 16 or 6 or higher then you have a new way of lazy loading your routes because re-act 60 node 6 adds a new method on the re-act object.

The lazy method which you can use to load your data your components asynchronously.

Which means only when they are needed.

And let's have a look at how this works now.

So re-act lazy is a method that was added with re-act 60 not six.

That allows us to load components asynchronously which means they are only loading the code behind them is only loaded when they are really required when they are being rendered.

And this is for example useful when having routing in your application because only when a user visits a certain route that component will be required and re-act lazy allows you to defer the rendering and the loading of the code of that component until it is required.

And that of course means that you don't load redundant code in advance.

It's not just useful for routing.

By the way whenever you have a use case whereas some component is loaded at a later point of time for example because you have a check and some condition needs to be met to render a certain component in all such cases you could use re-act lazy.

But let me show you how it works.

So let's go to the last Fall and here I'm using re-act router Dom to set up my browser router I'm using

Riak fragment here which is a feature that was added with re-act 16.00 2.

It's basically the same as our alks component we traded manually.

It's basically a component that you can use to well wrap over all components because you always need that wrapping component and react.

It does not render a real Dom element and therefore does not distort your dom.

And instead of that fragment I have a little dummy navigation and then I have three routes here and

if you have a look at that we are on the welcome page by default and we can switch to the user and the

Post's page.

OK so that is this application.

Nothing fancy thus far.

Now we could use re-act lazy to only load the user into posts component when we need them.

Right now everything is loaded in advance but we might never visit these routes.

So loading the code behind them in advance is not ideal.

If there were an even bigger app with more code behind these components the issue would of course be

worse.

So we want to load these two components only when we need them and we can do that with this new method.

How is this method used.

Well let's start with the Post's component instead of importing it like this which will always force

today that will be loaded in advance.

We need to use dynamic import just as we did with that async component we created earlier and this module

we need to use dynamic import.

So we create a constant for that which we named posts.

You could name it whatever you want.

I just name it posts so that I can continue to not use that name down there.

And the value of that constant year will be a call to react dot lazy.

This new method that was added with re-act 606.

Now let's move these imports to the top.

Do not get any Lanting warnings.

And now instead of re-act lazy we'd pass a function.

Here I'll use an arrow function which returns an import statement and this is a dynamic import.

Which means it's basically executed when this code runs and react will executed when we try to render

this component.

And here we are again still point to a file which contains our post component and important for that.

We should use default exports named exports are not supported.

So now I'm importing my post component but only when this function runs which means only when re-act

thinks that we need to use it and react to things that we need to use it when it detects that it needs

to rendered it.

Now with that changed let's go down to that route here and there we now need to make a little change.

Instead of using that component let's use the render method here.

There we would receive all these Raut props.

But in the end here I want to return something I want to return a computer component that should be

rendered and there I now need to import a new component from re-act suspence component with an import.

That is what I want to render here.



Suspence like this.

And in-between all render posts.

So my constant as a component here and now let's add one more thing to that suspence component.

And that's the fallback proc which should be J as X code and they all add div where I say loading and

this will actually be displayed.

In cases where re-act basically postpones the rendering of this wrap component and shows as well fallback

in the meantime.

And of course that doesn't have to be a div with loading that could be a spinner or anything like that.

And now with all that let's save it go back to the front page look at the user's page load the Post's

page all working.

So what's special.

Well we can see what's special when we reload the page and then go to the Network tab.

Now after reloading clear it and now click on the post page and you will see that there it loaded a

new file and that is the file holding the code for this component and that is async rendering at async

loading in action because this component and its code is only fetched and rendered when we really need

it and therefore we avoid loading everything in advance which can of course drastically improve the

performance of your application depending on its size.

So this is a neat alternative to the other way of lazy loading pages which we had before.

A great advantage of this approach is that we of course can not just used is in a routing scenario.

We could of course also have a scenario where we don't use that browser router so let me comment all

that out.

And instead let's say I have a simple button here where I say toggle mode or anything like that we add

a new method to this component here.

Mode handler

and we add a state where we say show and it's false.

Initially let's say and then there I call this set state in the function a form of said States that

we can access the old state we return the updated state or our update to just state and I'll show you

the opposite of what it previously was.

So did I toggle that show mode.

And of course you can also add name to it differently.

Now we have that button.

Now I bind on Click here to my.

This mode handler.

And now I just want to render either the user or to post page.

Depending on that mode of course can also name that show posts for example up the détour too.

And now let's add a simple check where you check if this state show posts.

If that is true then I want to render my posts and data will also grab this code which suspends of course.

Let's copy that and move it up there.

Common that back in put dead in brackets.

So one to render with suspense suspends my posts show posts is true.

Otherwise I'll render my user component like this.

Now since I have two adjacent components here I'll again use re-act fragment or use you alks component

of course and wrap this.

And now if this change if I go back and I click on toggle mode we see that chunk was loaded and we see

the post page.

So here we all take advantage of this.

A sync rendering and that is really something useful and a great addition with re-act 6:16 we'll see

more on that async rendering thing in future versions.

And right now this is what we can use re-act lazy.

Please be aware that this will not work if you're trying to serve a side rendered.

Then this is not support that this API will not work yet.

But if you have a client side rendered application as we have it here and of course then this is a great

addition and definitely something you want to check out for cases where you conditionally render some

component needed in the if statement or be dead in a routing scenario.

Now of course one thing to keep in mind the benefit you will get out of this will be greater if you

have larger chunks of data behind your components.

If you have very simple components using suspends might actually be overkill and could even slow down

your application or be suboptimal.

At this point of time so lazy loading the code of course shows its full strength.

If we're talking about bigger chunks of code.

you load components asynchronously,

and as I mentioned this is extremely useful in bigger apps where there are bigger chunks of code, a whole feature area in your application for example which might not even be visited by the user so you can save that code up front to only load it when needed.


### Routing & The Server (Deployment)
We're almost at the end of this routing module, a lot of content was covered here.

Now there's one important thing you have to know regarding routing when using the react router, when

it comes to deploying your app to a real server because you won't notice it here on the development

server because it's already configured correctly.

You have to remember how handling requests actually works in the web.

We have the user who sends a request to the server and we have our react app which is then loaded on

the index.html page.

The thing is before we load to index.html page the server needs to find out which page the user actually

wanted to visit.

That of course is the case because the server always handles requests first,

this is how the Internet works.

The problem is it's the react app which knows the routes.

So if we visit /posts, there is no /posts route on our server, that is defined in the javascript

code which is loaded on the index.html page which we never get because we get a 404 error on the

server because we tried to visit a route which is unknown to the server.

And clearly this is not what you saw during development because as I said the development server is already configured correctly.

We have to configure the server in a way that it always forwards requests no matter if it understands them or not, so also 404 error requests to the client, so that it always returns the index.html page, also for unknown requests because this then allows react to take over and parse the request against the routes it knows.

So we should always load index.html

and if then there is a request we dont know,

well you learned how to handle 404 errors with the react router.

Now as I said, the development server we used here already is configured to always load the index.html

file.

It is something you will also have to do when hosting the app on your own server though,

always return index.html

even and especially in 404 error cases.

There is another thing you have to be aware of when hosting your app on your server,

if you are hosting it on let's say example.com/

so if that's the page with which we're landing on the root page of your react app, you don't need to

set up anything special. But if you're serving your app from let's say example.com/myapp, so

anything beneath that folder should be your react app,

you need to tell react about this,

the react router to be precise.

You need to set the base path for the react router and I want to quickly show you how to do that. In your

application,

in the place where you use browser router,

so in our case in the app.js file here browser router, you can also configure that and you really

need to do that.

But there is a base name prop you can set and by default, that's set to slash.

So this is the default which you don't need to set.

If your serving your app from myapp, you should set this to /myapp, then all your requests are

routed against myapp/ and then the link you were pointing to.

Otherwise, if you had a link like here,

if you push the page change up on clicking a post, here we navigate to /posts and it would always

add this to your root domain.

Now if your react app is served from /myapp, it will only work correctly and add it to the

end of your domain /myapp

If basename is set up. So whenever you are serving your app from a sub directory, make sure to set basename.

So here I will remove basename or I'll duplicate it and comment it out to leave it here for reference and

remove it in the browser route

we're actually using, but this is something you have to know.
