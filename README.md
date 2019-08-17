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

## Section 12: Adding Routing to our Burger Project 
### 2. Building the Checkout Container.
So let's implement this checkout component.

I'll actually implement it as a container because it will be a component which manages its own state

and also passes pass this down to other components.

So I'll add a new folder in containers and I'll name it checkout and in there, I'll add a checkout.js

file which should hold my checkout component.

It'll be a class-based component since state will be involved and yes of course a functional component with useState hook would work too but as for the rest, I'll stick to class-based components for now.

So therefore, I extend the component object which I have to import together with React from the React package itself to support JSX and correctly set up that class-based component.

So let's add this class,

let's then export it as the default of this file and then let's plan how this checkout component should

look like and should behave. What I want to have in the checkout component is a tiny summary of the checkout,

so basically what the user is about to buy and the price probably and then a button to cancel the checkout

process and go back to the burger builder and of course, a button to continue.

And I guess for the summary, it would be nice to not again show just a list of the ingredients but maybe

show the burger itself, rebuild the burger in this checkout summary. So that's the goal here, show the

summary and then when the user clicks on continue, I then want to load the contact form, so step-by-step.

The goal therefore is to create a checkout summary form which allows me to display a review of the burger

and show the continue or cancel buttons. For that, I'll go into my components folder and add a new folder

in there which I'll name checkout or maybe order to replace all order related components there like the

checkout component and checkout it should be named checkout summary maybe and in there, I'll create a

CheckoutSummary.js

file and a CheckoutSummary.css file for the styling.

Now let's have a look at the CheckoutSummary.js

file, there I'll use the functional form to create the checkout summary component,

so basically just the checkout summary function here as you know it.

We will probably receive some props to render the burger and then return some JSX, so therefore we

definitely need to import React from the React package

and of course as always export checkout summary as the default.

Now the goal is to display a preview of our burger here and then show the continue or cancel buttons.

So what I'll do is in the JSX which I want to return here,

I'll first of all wrap this in a div which I'll also use for styling purposes to give this component

some style,

then I want to have a h1 tag where I say we hope it tastes well, something like that and thereafter,

now I want to have a box div basically where I want to preview my burger component.

This div is required to set the boundaries of the burger component and of course I'm going to reuse

my burger component which I already have,

that's the cool thing, we can reuse it.

So I'll set some inline styling here on that wrapping div which will hold my burger just to set the

width of let's say 300px and then also a height of let's say 300px and let's then also set

the margin to auto here.

Now inside that div, I want to use my burger component, so I need to import it. I'll import burger from and now navigate

up into the burger folder and there it's the burger.js file,

this is our burger component which I can now conveniently add like this,

the burger, a self-closing tag. I there also need to pass my ingredients and for that, it will of course

be important to know how I receive these ingredients.

I assume that for now I can simply just set the ingredients property of my burger component which it

does expect, if we have a look at the burger component,

we have props ingredients in there which we use, so I should also pass this to this

component,

not order summary, checkout summary, here we are.

So we expect ingredients in the burger, so we should pass it and for now I'll just expect that in the checkout

summary component

I'll also get an ingredients property which I then just pass on. Below that, I then want to show my

buttons and for that, I'll import my own buttons I built.

So the button component from the UI folder and there from the button folder and then the button.js

file of course and these buttons

as you probably know support two different styles,

we have the success and the danger class here which we can pass and we do pass it with the button type property.

So I'll add my buttons below

there, I'll add the first button where I'll set the button type to

let's say danger with a capital D because that's the CSS class name where I simply want to say CANCEL,

maybe all caps for styling purposes only and then I'll duplicate it to also have a Success button with

a capital S where I will say continue.

So these are the two buttons,

you also know that the buttons expose the click property which simply indicates that we clicked on the

button.

So that is something I'll also need to do,

let's split this over multiple lines, implement clicked here and then do something upon a click.

Now that is something I will add, for now I just want to finish the styling of this component.

So with that, we got our checkout summary.

JSX code,

now let me also assign a class name here to the wrapping div and this is a class I want to set up in the

CheckoutSummary.css file. I'll add that CheckoutSummary.css class here

because remember, we're back in our course project,

we're using CSS modules here to scope our styles.

There I'll set text align to center to center everything.

I'll set the width to 80% maybe and the margin of auto to the center this div or this element

and I'll add a media query where I check if we have a minimum width of 600px at which point of

time I simply want to limit the width so that it's no longer 80%

but here I will limit it to 500px.

Now with that, I have to import these CSS code or the classes object to be precise from CheckoutSummary.css

and then assign it here,

so here I'll add classes checkout summary,

taking advantage of CSS modules here.

Now we get the checkout summary component,

I now want to use that in my checkout file, in my checkout container to be precise.

So there, I'll quickly import the checkout summary component

we just created from the components folder therefore, there I created that order folder which holds the

checkout summary folder and there, the CheckoutSummary.js file.

Now inside my checkout component where I'll implement a render method, where I then of course return

some JSX, there I want to have a div which wraps my entire page because this will be used as a page

with the React router of course

and in there, I'll now add checkout summary, like this.

Keep in mind, checkout summary expects to get ingredients as a prop, so I should pass ingredients here

and that of course is an interesting question,

where do I get my ingredients from? For now,

I'll simply pass a dummy ingredients object but of course this is something I will replace.

I will add state to the checkout component and there in the state, I'll add ingredients and ingredients

for now will be salad one, meat one, cheese one and bacon one and this again is just some dummy data which

I'll replace.

So for now, that allows me to pass this state ingredients, we will have to use routing to really pass

ingredients later.

Now we get the checkout container here,

I now want to use it of course and for that, I will hardcode it into my app.js file right below

the burger builder.

Here I'll import the checkout container from ./containers/checkout/checkout

just to see how it looks,

we will load it via routing soon.

Make sure to save all files and make sure npm start is running and thereafter if you visit your page,

we get an error regarding the on click listener

but that shouldn't be a problem right now.

This is how it looks like, our checkout summary component,

now we can see that somehow this div with the burger is not really centered,

so this is something we should fix.

For that I'll go back into the checkout summary where I use the burger and one thing I should adjust

here is that I should use width 100% to take the full width of the checkout summary component.

Now with that, that looks much better on both small devices and bigger devices.

Now on small devices here, we got a little bit much height, this is something we can fix by disabling

this height to not always setting it to 300px,

so let's just get rid of the height property here

too, for the styling, that was a little bit too much.

Now we can definitely use that on mobile devices and on the desktop,

this looks good

too. Now of course, there still is some space but we need some space for bigger burgers,

so this is deliberate

but the main thing I now want to work on is that I don't always display this but instead this should

be displayed if I click on order now,

continue, then I want to load the checkout summary instead of the burger builder,

that's the goal and for that of course we need routing. Now feel free to go ahead and implement this on

your own and then compare your solution with mine which I'll start building in the next lecture.

## Section 14: Redux
### 1. Module Introduction
Welcome to this module, this is a core module in this course,it's about redux.

You might already know redux, it's often named together with react but it's a standalone third party library.

It is a library often used in react projects though to make state management, the management of application state easier because that can be hard in more complex react projects.

We already saw that in our course project, there we already had some cases like where we have to pass data around through query props, where state management became unnecessarily difficult.

Therefore in this module, we'll learn about redux, a solution to this problem which can help us make our state manageable again.

For that, let's first understand what exactly state is and what exactly redux then is and how it works.

### 2. What is State? Understanding State
So what is state?

Let me give you some examples.

State for example are the ingredients we added to our burger, that's part of our application state, the application state of our burger builder application.

The information, which ingredients we added is crucial because it determines what we need to render to the screen, how should our burger preview look like there?

It's also important behind the scenes when we store that burger on a server and we need to submit all these ingredients in the HTTP request. 

Another example would be the question, whether the user is authenticated or not, that can be super important as it might determine the options we're showing in the menu or the access we're granting to certain components.

Also interesting is UI statelike is a given modal open, is a backdrop open, should it be open?

That's super important too, it's less about data like ingredients and user authentication is, it's more about our pure UI only state.

It might only be relevant to one single component, still this is also an example for a state, more of a local than an application wide state but still, state determining what should get rendered to the screen and that is in its core what you can boil it down to, state influences what you see on the screen.

So therefore our last example would be a list of blog posts which we render, which we might filter, where we might need to know which of these posts were created by the user, also important state we might need in our application.

And of course the list goes on and on, you can add more and more examples here, now these really just are some examples. What's now so complex about state?

Why do we need extra library for that?

Let's take a closer look.

### 3. The Complexity of Managing State
State management can be very complex, react is great at reacting to state changes and updating the UI accordingly but managing that state can get very difficult as our application grows.

Of course react gives us the built-in state property which we use thus far but we could already see in our burger builder project that passing the ingredients from component A to component B can be very difficult and we had to use routing query parameters for that, certainly a workaround but not a very elegant one.

So state management should be easier, the example from the burger builder is a classical example, nothing special. 

Consider this application which is not the one we built, 

It's an app with the root app component and then a user is in a products container and some subcomponents.

Now let's say we have authentication added to this application, so users can sign up and sign in, to access the dashboard in the users area, we need to check if the user is signed in and only grant access if that resolves to a true.

Now checking that isn't too difficult because we're probably managing the authentication status in the auth component over there.

The problem now is what if we all need that information in a totally different area of our app like in the burger builder where we need ingredients in a totally different area of the app in a checkout. 

If we need information there, we somehow have to create a connection between the aut component and our card component here.

Well that is super complex and a very long chain of props or query params or however we manage to pass data around.

It's a pity that it is this difficult because in the end, we're writing javascript right and we're having a bundled javascript file as output or a couple of bundles if we're using lazy loading.

So in the end, why can't we just set some global variable which is a javascript object which stores our entire application state and which we can access from anywhere, why do we have to take the complicated route with query parameters if all we do is just use javascript in the end? 

The reason is that REACT's reactivity system doesn't react to changes in some global variable you defined and it's good that it doesn't, that makes it so efficient.

However, having this global store still sounds very interesting and that's exactly what redux is about as you will learn.

So let's take a closer look at redux before we then implement it to see how it works in action.

### 4. Understanding the Redux Flow:
So redux to the rescue, redux is awesome, right?

It allows us to solve all our problems, doesn't it?

How does redux work then?

Well remember that idea of having some central place where you manage the entire state, I said that we can't use a global variable for that and we can't but redux gives us a certain flow of data, a certain way of managing data that we can then nicely integrate with another package into the react app, so that react does react to changes of data.

Now we'll show you how that integration works but first, let me describe her redux works.

How does it manage data and how does it update it? 

In the end, it's all about a central store we have in each redux application.

And I want to highlight that redux is a third party library which works totally independent of react, it's most often seen in conjunction with react but theoretically, it's independent.

So it's all about a central store, this store stores the entire application state, it's that simple, you can think about it as a giant javascript object.

Now in a react application and again, redux is independent from react but it's the most common use case and it's a react course here in the end.

We've got components and a component probably wants to manipulate or get the current application state, now it doesn't do that by directly manipulating that central javascript object, that would not be picked up by react's reactivity system and even worse, it would make our store pretty unpredictable. 

If we added it from anywhere in our application, that we can never see where we made a certain change that broke our app, for example.

So we need to have a clear, predictable process of updating the state on which we can rely on and which is the only process that can change our state.

That is actually what redux is all about, having a clearly defined process of how your state may change.

The first building block besides the central store are actions which are dispatched from your javascript code, in a react app, they are dispatched from within your components. 

And action is just information package in the end with a type, something like addIngredient or removeIngredient, so a description you could say. 

Possibly, it also holds a payload, for example if the action is addIngredient, we need to also pass the information which ingredient and that would also be a part of the action.

So it's a information package we're sending out to the world or to redux to be precise, that action doesn't directly reach the store, that action doesn't hold any logic, it doesn't know how to update the store, it's just a messenger. 

The thing changing the store is a reducer.

Now here I've written reducers because we actually can combine multiple reducers into one but in the end, you'll end up with one route reducer which is directly connected to your store in the end.

So the action reaches the reducer and since the action contains a type, the reducer can check the type of the action, for example if it's addIngredient and we then define the code for that type of action in the reducer. 

The reducer in the end is just a pure function which receives the action and the old state as input and which then spits out an updated state.

The important thing is that the reducer has to execute synchronous code only, no asynchronous code, no side effects, no HTTP requests, nothing of that, you'll learn later how you can still implement asynchronous code but in reducers, it's just input in, output out, nothing in between, no delay.

So this is the reducer and the reducer spits up the updated state which then is stored in the store again and replaces the old state and that has to be done in an immutable way, so we always return a new state which can be based on the old one but which is technically a new javascript object, because objects are reference types in Javascript and we want to make sure that we don't accidentally change the old one.

So that is how the reducer handles the action, now the store is up to date.

How do we get the updated state back into our component then? For that, we use a subscription model.

The store triggers all subscriptions whenever the state changes, whenever the state is updated in the store.

And of course our component can subscribe to store updates and it then receives that update automatically, this is how simple it is.

It works through a subscription model and we simply say hey I want to get notified whenever the state changes, just as we say hey I want to change the state, here is an action describing my plans.

This is the redux flow, this is how redux works, very theoretical though. Let's see it in action over the next lectures.
![alt text](https://github.com/buiminhhai1/react-js-udemy-note/blob/master/Redux%20to%20the%20Rescue!.PNG)

### 5. Setting up Reducer and Store
The simplest reducer you can write simply returns the old state, so this is a valid reducer though of course it does nothing, it just returns the state you already had.

But we can already use that reducer and pass it as an argument to createStore rootReducer, with that, our reducer our store is created with that reducer in mind and now we have a created store, however this store will hold an undefined state.

We can verify this by console logging store and there, getState, that's a function we should execute and it will pull out the state from the store.

### 6. Dispatching Actions
In the last lecture we set up our root reducer and the store.

Now I want to use that store and not just output it with this console log statement but also dispatch an action. An action is dispatched by simply accessing the store, so this store constant which holds the created store and on that store concept, we can call dispatch. Dispatch is a function

and now important, this dispatch function here takes an argument and that argument is an action, that

should be a javascript object which needs to have a type property.

So don't mistype or anything like that, it's just type, make sure to spell this correctly.

This will later be important building block in getting the information which type of action was dispatched and what we should do in the reducer, that is why type is so important.

Type then is just some unique identifier of your choice.

The convention is to use all uppercase string, for example INC_COUNTER, for increment counter,

now you can use whatever you want here but this is the convention, all uppercase and be descriptive whilst

also being short about what you're doing when this is dispatched.

Now I said you can also pass some optional payload, we'll do this with the next action. Besides INC_COUNTER,

let's also emit ADD_COUNTER.

Now inc should increase it by 1

so we don't need to pass any extra information

but ADD_COUNTER should actually add a specific number to the counter and that value needs to be passed

along with the type. Now the type is the one property you have to use like this,

you can add any other properties you want to this object now, you can add value, name, ID whatever you want

or you add one additional property which you might name payload or any other name you like which then

could in turn be a javascript object grouping all the data you want to pass with the action.

This is totally up to you,

I'll not pass a payload object because I only want to pass one other field of information, I'll name it

value

but again, the property name is totally up to you and I'll set value to 10 because I want to increase to

counter by 10

and of course, you can pick any number.

So now we're dispatching two actions,

what do you think does this do to our store?

Let's console log store getState here and before we execute this, I want you to guess what will

now be our state, our counter in the state,

what will it now be?

So do you have an opinion?

Let's find out.

Let's rerun node redux-basics.js and

let's see what it spits out.

We get counter zero twice,

the first is from the first console log statement right after creating the store,

the second stems from this console log statement which refers to when we dispatched our actions.

So here, we still have a counter of zero,

did you think we would have a counter of 11 here

because we incremented it by one and then add a 10?

Now this would somehow be expected

but of course we haven't added any logic to react to these different action types.

We could have also dispatched something,

it wouldn't matter because we don't listen for the action type anywhere.

This is what we'll now add, in our reducer

we get the action as a second argument

so of course, we can react to different types of actions.

We can add an if statement and see if action.type

and we noted a type property will be there because I said that it is mandatory on every action we dispatch,

so we can check if action.type is for example INC_COUNTER. If it is inside of the if statement,

I want to return something else. Now here,

one important thing, you don't set state counter plus plus which would increment it and return state because

this is not immutable,

you're mutating the original state here.

So what you instead do is you return a new javascript object where you may first copy the old state with the spread operator, state and then overwrite the one property you want to adjust, so the counter and if that also would be a javascript object, you would have to copy it first too so that you never mutate any data, never, always do this immutably.

Here thankfully, counter is a number so I can simply take state.counter to get access to my old counter, just read access so I can do that, I'm not changing anything with that expression and now plus one.

And this gets now stored in this counter property which I add to this new javascript object where I first of all copied the properties and values of my old state.

With that, I'm returning an updated counter or an updated state with an updated counter upon the INC_COUNTER action here.

And of course I can duplicate this if statement  now to also do the same for ADD_COUNTER, so if we don't make it into the first statement, maybe we make it into the second one if the action type is ADD_COUNTER. Here however, I don't want to add one, I want to add action and now its value because I've specified a value property here in the object I dispatched.

Now with this, we only return state if none of these two if conditions applies, so now if we save this file and re-execute node redux-basics, we see a different output.

We get counter 0 for the first log which is executed right after initializing the store but after dispatching the two actions here, we actually get a different output for the second log where the second counter is 11 because we incremented it and we added 10 to it.

This is now actions and dispatching of actions in action, however one thing is still missing, the subscription.

Let's take a closer look in the next lecture.

### 7. Adding Subscriptions
So over the last lectures, we added or we created our store and we added actions, now I also want to add my subscriptions. Subscriptions make sure that I don't have to manually call getState here in my code if I want to get the current state snapshot but to inform me whenever I need to get a new state because something changed, because if I manually do it like here in a console log, I always have to guess if something changed.

So how do I create a subscription then? 

I access my store and there, I have a subscribe method I can execute. 

Now subscribe takes an argument, a function which will be executed when ever the state is updated, so whenever an action reached the reducer. 

The function we passed to subscribe doesn't get any arguments, so here I'll use the ES6 arrow syntax with empty parentheses, and then in the function body, we can execute any code we want on state updates.

So here, I'll log subscription, just a marker so that I see where this is coming from and now, I can also reach out to the store and get my state there. 

The getState method is the same as before, the difference is that I now know that I should get the state here because I know hey something changed and that subscription actually, of course typically is set up right after the store was created so that we get informed about any future dispatches.

So I notice that subscribe comes before dispatching the actions and this function in the subscribe method will be executed whenever action is dispatched and mutates the store.

With that, let's rerun this with node redux-basics.js and what we see is we first of all get the output for the console log statement here after creating the store and then, I get two subscription outputs and then the output here after the action is patching.

Now I get the two subscription outputs not because subscription comes before it getState, before this console log statement but because it's triggered when ever an action is dispatched, which of course happens before I do this console log statement.

This is how a subscription works, it's getting triggered whenever the state is updated.

Now that's all nice and this is now showing us all the building blocks of redux, owever it doesn't show us at all how this fits into our react application.

So let's see how we connect redux to react over the next lectures.

### 8. Connecting React to Redux
So we learn about redux and the redux-basics.js file.

We don't work with that file anymore now, instead now, I want to connect my react application to redux and use the advantages of redux in it, so that in the end, I managed my state with this counter and the buttons here with redux. 

Of course for such a simple application like this one, redux might be overkill but it is good to use a simpler application to practice the basics, we'll then apply redux to our course project in the next module too, no worries.

Now we already installed redux and with that, we can create a store.

This store should be created right before our application or when our application starts, so the index.js file is a great place, this is where we mount our app component to the dom, so creating the store here also makes a lot of sense.

Therefore I'll import something and now I'll use the good old ES6 imports here from redux, so from the redux package we installed, and the something is the createStore function.

Then before mounting the app, I'll create the store and store it in a constant named store so a lot of stores are here I guess.

So I create my store with create store, now you learned that this takes a reducer as the input. 

For that, I of course need to create the reduced too and I won't do this in this file, I will have more complex reducers in react applications with a lot of code for different types of actions and therefore, we typically store that logic into their own files.

Now there are different set ups you can use but you'll often see that there is a store folder in your

project next to the containers and the components folder and in there, you can have a reducer.js

file,

this will now be the file where I'll export the reducer I want to use. Still the reducer is just a function,

a function which retrieves a state and an action and then has to return a state, that doesn't change

a bit.

I will then export this as the file default so that we can use it outside of this file and I will also

set up an initial state here,

a javascript object which should reflect my initial state for that reducer. I'll set this to counter zero

here too because we have a counter in this application. Now I'll assign it here for my state, initial state

like this

and with that, we got a finished reducer.

Now we can import this in the index.js file,

so I'll add an import, import reducer from

and now ./store/reducer.js without the extension as always and pass that to create store.

With that we're creating a store successfully with our own reducer,

just like we learned before in the nodeJS file.

Now of course the reducer alone doesn't do that much,

we also want to connect this store which you just create and store in a constant here to our react

application and we want to be able to get slices off the state in our react containers, so that we can

display the state or render something depending on which state the application has.

And of course we also want to be able to dispatch actions, so connecting redux to react,

that is what we'll do next.


so here I'll simply wrap it. Provider is a helper component which allows us to kind of inject our store into the react components. For hooking up the provider component with our store here,

I read now manage this all internally. Well for that, we need to connect this individual container with the store or to be precise, in the end what we want to do is we want to set up our subscription here, we do this a bit differently than we did in the nodeJS file though, we won't do it manually by calling subscribe, we will use a feature provided by that react-redux package instead, let me show you which feature I mean. 

In the counter container and by the way, this pattern doesn't change, it's still our container components that managed the state, now they don't manage it on their own anymore but they are now the places which receive it from redux.

We still use container components which then may distribute it down to their components which they embed but we never change our pattern of having a few selected components getting the state and passing it on,

this pattern is still the same even though we'll eventually get rid of state later.

### 10. Pasing and  Retrieving Data with Action
In the previous assignment, we added three new actions we can dispatch and we do dispatch them in our counter container, decrement,add and subtract. 

Now for add and subtract which we obviously handle in our reducer, it wouldn't make sense to also receive a payload, some additional data passed along with the action type because right now, we have hard coded +10 and -8 into the reducer but of course, in a lot of applications for example when creating a new blog post, you would get that information from your component, the input the user entered for example, the ID of the post the user clicked on, you can't hard code that into your reducer for that reason.

So let's also say we don't want to hard code the value by which you want to add or subtract to the counter or from the counter into the reducer, instead we want to get this information along with the action, so we can easily implement this. On our

action here,

we are just dispatching a javascript object and only the type property is set in stone,

so to say. We can obviously add more properties to that object,

no one is stopping us from doing that, we can simply add a second property for example value or just V

whatever you want,

you could choose any name you want here and you can of course also add multiple properties.

So I'll take value here, though

what you also often see is just payload, payload could then itself be a javascript object which holds

all the relevant payload to this action.

But that's just something you often see,

you can also skip the payload and just have a value and let's say that's ten and a name and that's Max,

so you can add as many properties as you want.

Now here, I'll add one which I'll name val,

again the name is up to you

and let's say we always want to add 10.

And of course since we're inside the container, we could easily connect this to some input field

we have. Now for subtract, I'll add val and let's say this is 15,

so now I pass the value which I want to add or subtract along with the type

and again, the type property is the only property you have to have where the name is not up to you.

Now we can extract that value property in our reducer,

so here for add and subtract, I no longer want to add 10 or subtract 8,

instead here in the add if check, I'll simply add action.val and here the property name val is of

course the property name I chose here in my counter container, in

this object I pass in this action, so with the action I dispatch,

val, and the same of course for subtracting, here I also simply use action.val.

So I as a developer of course know what I named this property when I dispatched the action and I have

to retrieve my value or the data which is relevant to me in the reducer from that same property name.

Save all the files and get back to the application,

now the labels are wrong here we're subtracting 15 actually

but let's click the buttons to see if it works.

Let's subtract and we subtract the 15 and we can't add 10 again because we set val to 10 for this button.

So let's quickly update the caption on the other button so that it doesn't say subtract 8, but instead that it simply

says subtract 15

and now our application is 100% up to date. Now though and that's important,

passing a payload with the action, passing some additional data and not just passing the type.


### 12. Updating State Immutably

Now that we learned how to restructure our reducer a little bit here, let's dive into more state management.

Let's add a new state here, let's maybe name it results, so a new property to our state I should say and initially should be an empty array.

Now let's go to our counter component here and there, I want to add a new button, 
so I'll first of all add a horizontal line with just hr, self-closing element and I'll add a normal button here where I'll simply say STORE_RESULT, like this and this result should get added to an unordered list, this all has no styling right now which I create below that button.

Now the idea is that when I click STORE_RESULT, that I simply add the current counter value to my result list here, so for that of course I want to dispatch an action whenever this button is clicked and then push this new result to this results array, update that array with it and of course, take the current counter as input.

Additionally if I click one of these results, so one of these list items, I want to remove it from the array, so it should have an ID, something like that by which I can identify it and I want to remove that list item thereafter. 

For this, I first of all will start here in my container component even though I haven't worked on the reducer or anything like that and I'll simply add two new props 
to mapDispatchToProps because I need two new functions basically, two new dispatch functions.

One could be on STORE_RESULT,

this should hold an anonymous function where I dispatch, I dispatch a javascript object which needs to

have a type,

this could be STORE_RESULT and the value should be a current counter value of course.

Now this is something I don't need to pass as a payload though because since the counter is part of

my application state, I will have access to it in my reducer anyways later,

so I don't need to pass it here as payload.

Of course you could also have use cases where you want to store some result the user entered, then you wouldn't

pass it as a value from your component, here

however, it's not required. I'll then duplicate this

and I'll also set our property which I'll name onDeleteResult, where I want to dispatch an actual

let's say with the identifier, delete result.

Now I have these two props and I'll connect them in my container, here

I'll add the onClick listener to the STORE_RESULT button and I'll execute this.props.onStoreResult,

no parentheses as always, this is just a reference to a method and it will get executed automatically.

And on the list item here, I'll also add a click listener where I'll say onDelete,

so this.props.onDeleteResult.

Now of course, this list doesn't have any content yet, we'll later dynamically create a list of items here,

so for now, let's focus on this button here with the STORE_RESULT prop, when we click this button,

right now, I have the console open, nothing happens.

We also don't get an error, notice this,

so you can dispatch actions which you actually don't handle in the reducer,

that's the first important takeaway. We are dispatching STORE_RESULT here because we're binding on store

result which executes this method,

we're binding that to the button,

so this action does get dispatched and it does reach the reducer because we only have one single reducer

in our react app and therefore all actions make it through that reducer.

But since I simply ignore it here, I have no case handling action with the type STORE_RESULT, I get to this

line here where I return the current state,

that's it.

I just returned the current state which also means that if I changed the counter through my buttons up here

and I click this, I don't reset the state,

I don't return the initial state,

I return the current state,

so that's the first important takeaway.

But let's now handle this,

let's create a new case where I say STORE_RESULT and there, I want to return,

now I want to return what? I want to return an updated version of my state

and we should this immutable, right now in all the cases, we'll always return a new javascript object where

we only update the counter for the single reason that we only have the counter property there,

the whole state previously was made up only by the counter property.

Now we also have a results property which is an array and therefore right now, if we increment, decrement

add or subtract, we basically remove that from our state because we return the updated version of the

state and it just is a javascript object with the updated counter but without a results property.

And unlike set state did in react,

this is not merged with the old state or anything like that,

this is the new state instead.

So here, the new state doesn't have results anymore

so actually this is not how we should update the state,

instead we should copy the old state properties and then only update the ones which need updating and this should

happen

immutably. So what we don't do is we don't set const newState equal to state and then set newState.Counter

equals state.counter plus 1 and then we return newState here,

this is not how we do it.

Why do we not do it like this?

Because we're mutating the old state here,

instead what we do is we copy the old state.

Now one way of doing this is calling object.assign, passing an empty javascript object us to the first

argument and the old javascript object we want to copy as the second state here,

like that.

Now this will basically clone the old object in an immutable way

giving us a new javascript object which has all the properties of the old object but is a technically

different object and that of course is important due to the way objects and array work in javascript

with the reference types or these primitive types, if that is unclear,

definitely check this out,

it is a core concept of javascript.

Now with that we get a copy, though important, not a deep clone,

so our results array still is the same object as it is here in the initial state. But here it doesn't matter,

we get a copy of our state, the new state,

now there if we change the counter, we're not doing this in the old state but in that copied state and

we're returning that updated copied state.

This will then become the new state and it is a technically new object and that's important.

Now you can write it like this,

the shorter way is to simply return a javascript object and there, distribute all the properties of the

old state which you can do with the spread operator, state like this ...state.

This simply tells javascript return a javascript object,

take all the properties and values of the state argument which is our old state,

distribute these properties with their values in this new object and then since we define an additional

property, add this property to the object or if it already was present due to us distributing the old

state as it would be for the counter, this is part of the old state,

overwrite this but only this, leave results untouched.

This is what's happening here, we're distributing the old state, we're overwriting counter, we're not touching

results.

So this is how we should update the state in all cases,

do it immutably, don't touch the old state, don't just return a new object without covering all the properties

of the old state

or you're about to delete properties from your state, as we previously did.

And with that in STORE_RESULT, we also return a javascript object where we distribute the old state thus

keeping the counter

but then we set results here.

So this results property we want to update,

we can set an equal to state results and then we can call concat which simply is like push but where

push manipulates the original value,

concat returns a new array which is the older array plus the argument you add to concat.

So it's an immutable way of updating an array by adding an item,

it returns a new array, that's the key thing here

because arrays also are reference types,

if you would call push,

you are touching the original results property in the original state, even though you used the spread

operator here,

that doesn't prevent you from doing that

and this is not a good practice,

not how you should do it,

your state management becomes unpredictable if you do it.

So use concat and now push whatever you want to add to this array,

for example here we could add state counter since we want to store a snapshot of the counter and push

it to the results array.

Now with that, we updated our state immutably for all cases,

you learned how to update an array in your state

immutably with concat by adding a new item

and now, we can return that state here where we do return it here actually and we can use it in our

counter component. There we can now bind it in mapStateToProps to a new prop, maybe a stored results

prop which should be state.results, referring to that property name you set up in the reducer, results,

this has to be equal

so we're retrieving this state property and now, we can use stored results which we can access through

this props here in our render method.

So here for the list item where I want to output them, I'll do it inline here with curly braces,

I can say this.props.storedResults.map and now map each stored result which I'll store in this argument

here, I'll map it to this list item.

So I'll simply wrap my list item and put it into my map method here to as always map this array of

stored results into an array of jsx list items and there,

now we have our new list item where we of course can output stored result.

And now this would be our result

but actually, I want to go back to the reducer and change it a tiny bit,

I don't just want to store a number,

I want to create an object and this is kind of optional here but I want to do it because I don't just

want to have my result value

and you could name this val, v, whatever you want,

I also want to create an id here and that id should be something unique,

so I'll simply use new date which is simply a snapshot of the date when this was added.

Now I have an id and a value and now back in the counter component,

I can use both storedResult_value referring to that value property here in the object

I pushed to that array or I concat to this array to be precise

and since we have a list, we need to set a key that can set this key to storedResult.id, that date snapshot.

Now with that, if we go back to the application and I click Add 10 and I click store result, we see 10 here

added in the middle,

let me add 10 again,

now we store 20 as a second value,

So now we are storing

all these values. Clicking on them doesn't do much,

it also doesn't throw an error but of course we're not handling this

click listener where I want to delete the result and therefore dispatch delete result.

So let's implement this in the next lecture.
### Update Arrays Immutably
Use slice, filter, ..., concat to do this.

### Outsourcing  Action Types
If we have a look at our reducer here, we see that we have all these different cases, incrementing, adding and so on, delete, store result, all these things.

And of course I emphasize that the identifiers we're looking for here in the reducer are the identifiers we should use in our container components, in our application where we want to dispatch these actions.

We do so of course but there always is the danger of us simply adding a tiny typo and searching for it for hours because we don't find it. 

Therefore it is a good practice to outsource your action types into constants you can use in your application so that you always just import a constant and eliminate the danger of mistyping, this is especially useful as your application grows.

If you only have two types of actions you dispatch, you might not need that but for bigger applications, definitely add it. For this, I'll add a new file to my store folder and I'll name it actions.js and in there, we can simply export a constant which you now typically give the same name as the identifier

we'll have.

So you could have a constant which is increment and the value we assign is just that string identifier,

so we just stored that string in a constant now which we export and we do that for all our actions,

so we also have decrement here and the identifier is the same.

Now theoretically, name of the constant and identifier don't have to match but it is a good practice,

then here we have the same for add

and of course for subtract, like this and of course also for store result which we also then use as

the identifier and delete result, like this.

So now we have this extra file where we export all these actions,

this now allows us to go into the reducer and import the actions from there,

we can now simply import everything from a given file and store it in some javascript object, maybe action

types from ./actions. actionType

now is a javascript object which has all these properties here or all these consts here I should say

as properties.

So now here, we can check for case actionTypes. and now here that would be increment and the same

of course for decrement and so on.

The huge advantage of this approach simply is we're now importing our constants here

and if we mistype one constant name, we'll actually get an error by our IDE or by that build process, if

we store and save everything, I'll get an error 'export Incement' not found

so I have to fix my typo to have a working application again,

this is why you use this approach. So I'll replace all my hardcoded strings here with the action

types

I'm importing, so subtract, add and so on to eliminate the danger of mistyping here.

So actionTypes.STORE_RESULT

and of course also actionTypes.DELETE_RESULTS so that all are replaced.

And then I do the same where I dispatch them,

it of course doesn't make any sense to still have hardcoded values here because I could still mistype,

so I'll simply now import my action types here,

so import everything as action types and this name is up to you,

you can name this object whatever you want from

and now I simply move up to the store folder to the actions.js file and now I use my action types here

too for dispatching.

So here the type is actionTypes.INCREMENT, decrement and so on

and therefore, we're now always referring to that property, to the constants we are exporting in the actions

file and hence we can't mess up by mistyping or having different identifiers because now we have only

one place where we set up and store our identifiers

and that is in this actions.js file.

So now with this adjusted, the application should still work as before,

as you can see I can still add and delete results and change my counter but now, we eliminated that one

danger, one potential source of errors

therefore outsourcing your action types into a separate file from which you then import is a good practice

especially as your application grows but it doesn't have to grow that much

for this to make sense.

### Types of State:
Before we finish this module and dive into more advanced redux concepts later such as running asynchronous code which we haven't covered at all yet, let me walk you through different types of state and answer the question, should every state be handled through redux.

Because in the demo application in this module, we eliminated the set state call in the component and we eliminated the local component state, the state we used thus far in all react applications and projects we built in this course, instead we used the redux state and action dispatching and store binding to use that state.

Is this always the approach you should follow, do you always have to use redux to begin with?

Well the question whether you use redux or not depends on the size of your application and the complexity of your state.

You have a simple, a small application, setting up redux might take you longer than the benefits you get out of it are worth it. 

For any decent medium size or big application, using redux and managing the state there is probably a good idea but then still, we have to ask which state should be used for redux because you shouldn't necessarily manage all the state in it.

Let's have a look at the various types of state, some examples and whether you should use redux for them or not.

Let's consider local UI state such as showing or hiding a backdrop, opening a modal, all these things which of course change the state to update the UI of your react application and hence to show something different, should you use redux for that?

The answer is often times, you might not use redux here, you mostly handle this within your components, that being said, you can use redux for that.

You can have show modal property in your global state, dispatch an action to set it to true and dispatch an action to set it to false then connect your component and listen to that property to conditionally render a modal or not but that might be overkill.

Often times, you can't handle that within your components just as we did it before.

Another important type of state is persistent state, this means the state you typically also store in server side databases like the users of your application or posts of a blog, all burger orders, stuff like that.

Now here, you typically do use redux but of course not for all the data you have in your service side database because redux of course is just for managing the state in your application as long as your application is alive. And always keep in mind, when the user refreshes your page, your state is gone so redux is not a replacement for a database, instead you store such data on a server but the relevant slices are managed by redux.

So the post you're currently displaying, the users you currently need to display, the post the user currently may edit, these things are loaded and stored in redux so that you have them available so that you can render them to the screen but that might not include all the data you have in your database.

And then we have typical client state, things like is the user authenticated or filters set by the user, so if you have a dropdown allowing the user to filter your posts, that's not data you store in the database, you can't store if the user is authenticated because if he enters the wrong login information, you don't need to store it on the server unnecessarily.

Also the filter set by the user, you might not store that on a server because it's not that important to store it in the database, you definitely need to be aware of the current filter settings on your client in your javascript code in the react application though. 

This is state you definitely use redux for, you managed that via redux because it might affect multiple components or areas of your application, for example if the user is authenticated, it might be important for a lot of components in your app and there, redux really shines because the central storage then offers a huge advantage.

So these are two different types of state and how you handle them.

Now we will see examples for all of that over the next modules when we also add redux to our course project.

Before we do that though, it's time to practice redux.

## Section 16: Redux Advanced
### 1. Introduction (Unleash The Full Redux Power)
Welcome to this module. Over the last two modules you learned the basics about redux, you learned what it is and why you might want to use it, we also apply that to our burger builder project. 

In this module now, we'll dive deeper into redux, dive into the a little bit more advanced features and see for example how we may run asynchronous code.

So let's start.

### 2. Adding Middleware
Before we dive into running asynchronous code, let me dive into a super important advanced concept we have when working with redux and with that, I always mean redux the package on its own, be that connected to your react app or not.

You may add middleware to it right between your action being dispatched and it reaching the reducer, this is where you can add middleware.

Now you might not know what middleware is, if you're a server side developer having worked with Express.js for example, you might have an idea though. Middleware basically is a term used for functions or the code general you hook into a process which then gets executed as part of that process without stopping it.

So we can add middleware and the action will still reach the reducer thereafter but we can do something with that action before it reaches the reducer, that can be simply logging something, but that will also become important later when we want to execute asynchronous code, so for now, let's see middleware in action by adding it to our project. 

To show you how middleware works, let me go into the index.js file, the file where we actually create the store.

It's at this point of time that we can also add middleware to the project and for that of course, we need to learn how to exactly do that.

First of all we need a middleware.

As I said middleware in this case here is just a piece of code, specifically a function.

Now I'll create my own middleware here, later we'll add middleware provided by other providers.

I want to create a simple middleware which simply logs each action we issue, so what I want to do is I'll create a new constant and I'll name it logger, this will be the name of my middleware so to say, of course the name of the content is totally up to you as always. 

This then takes a function and I will use the ES6 arrow syntax.

It will get the store as an input, this is the case because we will soon use a specific method provided by redux to connect our own middleware to the store and this method provided by redux will eventually execute our middleware function and give us the store.

Now the function body of this middleware function then looks like that, we return another function, so that can be confusing but this function simply returns another function.

I'll also write this other function in the ES6 arrow function syntax, this other function will receive the next argument, you can name this argument whatever you want but next makes sense because this will be a function which you can execute to let the action continue its journey onto the reducer, you might know this next function if you are an experienced express developer.

So this function which is returned here will also be executed by redux in the end, this function then and now it really becomes a bit confusing but this function now also returns a function, the last one though, which will receive the action you dispatched as an input, again this function will also be executed for you.
 
So this nested function party here is simply a middleware, now inside that inner function which receives the action, we can also access a store and this next function and of course the action itself.  

And here we can now execute the code we want to run in between the action and the reducer.

So here I'll add a log statement, mark it as middleware, so that's just for us so that we can quickly see where this is coming from and there I'll say dispatching and I'll print the action. 

Thereafter, I will execute next and here, important, this will now let the action continue to the reducer, though for that to succeed, we need to pass the action as an argument, now that's important because you could theoretically also change that action here in the middleware, we have access to it, we get it as an argument, we could change the type. 

Of course we should do that with caution because we can break our application or worse than that, we can implement unexpected behaviors.

So here I will call next and pass the unmodified action, the cool thing is I can now store the result of this call which I will need to return in this inner function, so I will return results here.

Now in between these two steps, I can log something else, so console log, log a middleware related log statement here and there, I will have my next state so I can simply called store.getState because I do have access to my store, we get it in the outer function, it's the normal redux store which you learn has to getState method, so I can of course call that in the middleware too.

So this function tree is in the end what gets executed, all of that is done by redux, we don't have to call any of these functions, all we have to do is apply this middleware to our store.

So how do we do that?

First of all, we need to import something from redux, so here besides combineReducers, I'll import applyMiddleware, this function as the names suggests allows us to add our own middleware to the store.

So here in create store where we initialize the store, we can add more arguments and the second argument here can be a so-called enhancer.

Now this enhancer is nothing else than a middleware for example, so here we can call applyMiddleware and now we can pass our logger constant which holds this function tree which happens to be a valid middleware executable by redux to apply middleware and therefore connect that to the store.

And this already is all here and actually, you can pass a list of middlewares here to applyMiddleware, they will be executed in order then. 

Here we only have one though, so let's save this and then run npm start to start this project.

This should allow us to still use the project as before but we should get additional output here on the right in the console.

So here if we click increment, we see two logs here, the first one is the dispatching log where we see the action we dispatched, that's the javascript object we dispatched and the second one is the next state where we see the updated state and that of course happens for every action we dispatch.

So this is our middleware in action, now of course the middleware can already be nice to do exactly that, log your state and see very well what's going on. 

Now a more useful use case for a middleware is to be seen later when we actually handle asynchronous code.

But first I want to stick to this idea of getting some insights into this state, it would be nice for debugging if we could always look into the store.

So if we had some logging but more than that, that even if we just didn't dispatch anything, we could still look into the current store.

Let's have a look at what can help us with that in the next lecture.

### 3. Using the Redux developer tool
You should see the redux dev tools open up here on the right, now it's saying no store found because we haven't followed the second step where we have to basically inform this extension that there is a store in our web app and for that, we simply need to set up a special variable here or pass a special enhancer we should say to our create store method. Since we're using a iddleware we have to use the advance store set up but it's still pretty simple. Let's copy that strangely named variable here on the window object, the redux dev tools extension compose thing here, this essentially is a variable which is injected by the Chrome extension into our javascript at runtime so it will be available. 

Back in our code in the

index.js file where

we create our store,

I will first of all as instructed here create a custom constant before we do anything on the store, I'll

name it composeEnhancers. This will then be our special variable or in case that can't be found,

we'll fall back to a default compose function provided by redux,

you can import it from the redux package.

Now compose is a little bit similar to combineReducers, combineReducers allows us to combine well

reducers, compose allows us to combine enhancers, applyMiddleware is only for middlewares if we have

other enhancers like the store dev tools, we need to use compose to compose a set of enhancers with both

the dev tools features and our middleware.

So we also add compose here, separate it with this or sign to take this dynamically injected variable if available

but if not, to still have to fall back to the native redux solution which of course doesn't give us dev

tools support then.

So now composeEnhancers essentially just holds a function,

if we go back to the documentation,

we see that now we should create our store and use this new composeEnhancers function which uses either

the dev tools function or the natively built-in one to then pass applyMiddleware to it.

So we'll do that,

I will wrap applyMiddleware in create store with composeEnhancers,

so with this constant name here composeEnhancers, wrap applyMiddleware with it so pass applyMiddleware

as a function to that,

you don't need to pass anything about the dev tools because it will be passed in automatically, if

that is chosen, so if that is available.

So we got a set up where we should be able to connect our browser extension to the store running in

our Javascript code.

Let's have a look, let's go back to the react application and there, you should already see that the

redux view here is filled with life.

Here you see all actions which were emitted, like the init action which happens first,

can shrink this to get a different view on this

and there you see for each action, what type this was or which payload it actually carried,

also anything besides type, what the state is at this point of time, how it changed the state

and you can always look into the state therefore with this state button at a given point of time.

Now if I dispatch a new action by for example subtracting 15, you'll see it gets added here

and if you click on it, we see what the state is after this action, this state here,

you also see the old state if you click on the action, on the init action,

so you see the state at different points of times. You'll see how the subtract action changed the state,

it deducted 15 off the counter and you'll see what the action carried,

that's pretty useful.

Now we can add more and more and we can always see how we adjusted our state and what our current state

is and what our state was in the past.

So redux dev tools are extremely useful and definitely dive into the documentation I pointed you to

to learn more about them.

Now one important feature I want to show you is the time traveling, with the redux dev tools,

you can travel through time.

So for example, of course the application we see here reflects the state after all these actions

but if we wanted to rewind and say yes let's go back to that subtracting here, you can click on subtract and

then on jump

and now you see you are back to that point of time where you just subtracted 15.

Now the old states are not lost,

you can always go back to there by clicking jump on that again

but you can also go back and for example skip this to update your state as if you haven't ever dispatched

this action

and of course, this can also be reverted.

So this is a extremely nice feature which gives you a lot of debugging possibilities and especially

more complex apps,

this is great to make sure that only actions are dispatched you expected to be dispatched and to

find out why the state is currently in

well the state it is in.

### 5. Executing Asynchronous Code - Introduction
utilize
### 6. Introduction Action creators
how does that look like? 
What is that? 
An action creator is just a function which returns an action or which creates an action, hence the name. 

An action creator would return such an object and you can see the benefit when we talk about asynchronous code. 

As I said action creators are useful for handling asynchronous code.
But le me also quickly elaborate on the question whether we should use them for synchronous code or not, 

it's a clean way of creating you actions, you have everything about actions in one file, you don't have to create the action object anywhere else. 








In the last video, we introduced some synchronous action creators, now I want to take advantage of them to handle asynchronous code and to handle asynchronous code, we need to add a special middleware to our redux project, a third party library we can add called redux-thunk. 

Here I'm on the github page, simply google for redux-thunk written like this to find it, here you can find more instructions on that.

Generally, this is a library which as I just said adds a middleware to your project which allows your actions to not or your action creators to be precise to not return the action itself but return a function which will eventually dispatch an action. 

With this little trick, not returning the action itself but a function which will then dispatch one, we can run asynchronous code because the eventually dispatched one part is the part which may run asynchronously, it'll become clearer once we add it.

So to add it, let's pause or let's quit npm start and let's install a new package with npm install --save, the name is redux-thunk, written like that.

Now with this, this will get downloaded and stored as always and we can then register it as a middleware to our project.

Detailed instructions can always be found on the github page of course, there you see that after installing it, in the end we just add it with applyMiddleware.

So let's go back into our index.js file where we create the store and add middleware and there, I'll now import this new package.

So I'll import something from redux-thunk and that something can be found on their page, they actually have a default export so we don't need curly bracers, we can give it any name we want, I'll stick to thunk but you can rename this to whatever you want, this package essentially just exports the middleware.

Now this already is a middleware, so behind the scenes it looks like our custom middleware, couple of nested function calls and therefore we can add it. 

Now here, in applyMiddleware I'll add it after the logger thunk, so that object we just imported, that function to be precise.

So this is the middleware added, with that we can go back to our action creators in the actions.js file and let's say in storeResult, we actually want to execute set timeout and only after 2 seconds we want to store the result.

So here in this function which gets executed, somehow in there, we want to return this action after two seconds to simulate that we previously or prior to this action reached out to a server to store it there and only update our state once this one's successful, for example. 

Now with that, with the current set up here, this won't work but with the thunk middleware added, what we can do is we can change this return statement here and I'll put it right in front of set timeout, we'll clean up the rest here soon, so I will add a new return statement actually which will return a function, that's important.

Now you can again use the function keyword, this function receives dispatch as an argument, the dispatch action, now we get dispatch in here due to redux-thunk. 

I said that middleware runs between the dispatching of an action and the point of time the action reaches the reducer, now the thing we do here is we still dispatch an action but then redux-thunk, the middleware comes in, steps in, has access to the action there, basically blocks the old action we could say and dispatches it again in the future.

Now the new action will reach the reducer but in-between, redux-thunk is able to wait because it can dispatch an action whenever it wants.

This is the asynchronous part and that is exactly allowing us to execute some asynchronous code inside of this function and of course, we can also use good old ES6 arrow syntax here, like this.

So the code inside of this dispatch function here is executed and now inside of set timeout, inside of this function passed to set timeout, we can execute dispatch to now dispatch whichever action we want to dispatch.

Now of course, we would create an infinite loop if we again dispatch storeResult here, our action creator.

So what do we typically do is we create asynchronous action creators, which in the end dispatch actions created by synchronous ones.

So what I'll do is I'll quickly create a new action creator and export it, I'll name it saveResult, this will now still be the action creator as we had it before receiving the result and there, returning

the action we use previously with type storeResult,

so that is my synchronous action creator. In storeResult

however, I will now dispatch exactly that saveResult action creator which returns me this action

which actually updates the state and the store because it is the action of the type we handle in the

reducer.

Now before we see that in action, we should make the flow clearer,

there's one thing we have to keep in mind, here in storeResult when we return this function which will

get executed by redux-thunk and where we have set timeout, where we then dispatch the action which

should run asynchronously and update the store,

we need to execute saveResult which is this action creator as a function of course and pass res

on

so the redo pass the payload to the store. With that,

make sure to save all files including the counter.js file and then let's restart npm start to see

if this works

and to also see the flow of events in our redux dev tools. So the app loaded, we can still manipulate

our counter but if I click storeResult here,

you see that it took two seconds to actually print storeResult.

Now that's the interesting thing,

you never saw this other action creator

with the set timeout inside of it lead to any output.

If I click storeResult, nothing happens immediately, only after two seconds we see storeResult.

So only the action dispatch in there after two seconds leaves a footprint because it's our synchronous

action and only synchronous actions may edit the store. The other action creators like storeResult

which runs some asynchronous code

are only possible due to redux-thunk and are caught in between,

they never make it to the reducer,

we only use them as a utility step in-between to run our asynchronous code which happens to be required

to run on a lot of actions and then dispatch the synchronous action to change the state in the store

once we are certain that we know what to do there,

so once our asynchronous code finished, this is why we see it here. In the console interesting enough,

where we have our logger middleware, if I clear that, you'll see that we get more output because the logger

logs everything which reaches the action funnel and that includes our function which is returned by

the asynchronous action. We never added the state here though because that gets blocked by redux-thunk.

So this is how we can work with action creators to handle asynchronous code in our redux store.

### 7. Restructuring Actions
So we introduced action creators in the last lectures and you learned that they are especially useful when working with asynchronous code because together with redux-thunk, that middleware, we could basically find a place to execute our asynchronous code when dispatching an action and block that original dispatching to then just dispatch another action, all that handled by that redux-thunk middleware once our asynchronous task is done. 

Now with that, we got this new actions file which not only holds our action types, so the unique identifiers so to say but also all these creator functions which use these identifiers. 
Obviously our file here in the demo project isn't that big, we can of course simply stick to one file but we also split up the reducers into counter and result and you typically also do that for actions as your application grows and you're going to see that in the burger builder project. 

Therefore I'll create new files here, I'll create a counter.js file and I'll create a result.js file, so just like in the reducers folder, now for actions. I'll rename the actions file to action types because here, I now only want to export these unique identifiers, so that I have one file providing all the action types my application knows and theoretically, you could of course also split up into multiple files.

Now I'll take my action creators and put them into their respective files so for the counter, I'll take the increment, decrement, add and subtract action creator, cut it from the action types file and put it into the counter file.

Now of course, this reference to this constant won't work anymore because that constant now lives in

a different file.

So I should import that and I will import everything as action types from ./actionTypes which

allows me to now set up my types by accessing action types and then the constants which we do export

in that file.

I'll do the same for decrement and of course also for add and subtract, like this,

finally also for subtract.

So that's the updated counter.js file with the action creators for the counter related actions,

of course I'll do the same for the result, take my saveResult, storeResult and this deleteResult

creator,

so that also includes the asynchronous one

and then I'll also import everything as action types from this action types file

and with that, we can also use the action types we import to assign the right types here.

So storeResult, in storeResult itself I just have my asynchronous code dispatching saveResult

in the end and then deleteResult, I of course also want to dispatch deleteResult.

So now I got my action creators outsourced, the action types file now only contains my action types and

exports them,

now I also want to have one file exporting all my action creators,

so I'll create an index.js file here and in there, I'll actually use a syntax you might have not

seen before,

I'll just export something from a file.

I can do that so I don't even import it in this file,

I just have one file, the index.js file

which groups

all exports from separate files, so that in the end I can always point to that file to import something

from any of the files I'll point to in that file here. So let me quickly do that, let's export something from the

counter.js file and that something actually will be a list of everything

this file does offer, like add, subtract, increment and decrement.

And this really is just an advanced feature if someone wants to use such a set up of the project to handle

a bigger project with lots and lots of actions and action creators of course,

it's overkill for this demo project but it will make more sense later when we reach our burger builder

and I want to teach you the concept right now already.

So I'll also export something from the result file here that will be storeResult and it will be deleteResult,

saveResult is not exported here though I could of course also export it but I'll never need it

in any other file so I won't include it into my grouping.

Now what this allows me to do is to later just import from index.js and actually import from any of

these two files which I group in this index.js file.

Now that's just a tiny improvement to make our files even a bit leaner, now what I also need to do is I need

to adjust my reducer file where I do import these action types, so in counter.js where I import action

types, that now lives in the actionTypes.js file in the actions folder, the same adjustment needs

to be made in the result reducer,

there I also now import from the action types file in the actions folder. And finally in the counter

where I dispatch, here I refer to action creators and that now actually should point to the index.js

file,

so /index. Let's quickly restart npm start to see if it really has problems or just is stuck in

the rebuild process,

we do find an issue in the counter.js file,

it doesn't like my imports here, action types,

oh because I mistyped here it's actions,

that's a typo in the file name, the file name should be action types.

Now with the file name changed, I need to change all my imports in the other action files too,

there I was referencing the wrong file, with all that adjusted to really point to actiontypes.js,

we should have a working application again just as before with asynchronous storage available.

Now however with a bit more split up action creators over multiple files, as I said for this demo project

overkill but definitely something you should keep in mind for bigger projects because what it allows

you is that you have files with only a few action creators in each file which makes it easier to find

that action creator you want it to change or check.

So this is why I chose that setup and it is something I wanted to show you for your bigger projects.

### 9. Where to Put Data Transforming Logic? 
Now we restructured our actions in the last lecture, now I want to dive into what we actually put into the action creators.

It's obviously easy for asynchronous code,the only place where we can execute asynchronous code is in our action creator, it's what redux-thunk is made for and it's the common and best practice pattern if you need to reach out to a server to fetch data from it and thereafter store it in your store,definitely do that with the action creator. 

Send your HTTP request here instead of set timeout and once the answer is there, the response is there, store it in your store, you will see this in action in the course project of course.

However you can of course put much more logic into your action creators, think about saveResult, we save our result there, we get it as an argument and we simply return an action where we pass it on as a payload.

Now this is a very dry action creator,it doesn't do anything else but just return object with the unchanged response,result, excuse me.

Now obviously what we could do is we could create a constant maybe name it updatedResult and set it equal to result times two.

Now obviously, that doesn't make this much sense here but we can theoretically alter anything you want here and you might have transformations which make more sense, maybe we want to update some id, we want to add a user name and we then pass on our updatedResult.

The thing is this happens upon saving the result, keep that in mind, our application still works. If I store that, we stored 20 because we updated the result by multiplying it with two.

Now we have logic in the action creator and this might be valid logic instead of some nonsense operation like this one, the thing is you could of course also execute the same logic so let me revert this to the previous state of just passing on response.

You could execute that same logic if you need to transform the data before storing it in the state which is perfectly fine which might happen.

You can execute that same logic of course in your reducer, here storeResult, here we concatenate the result and store the value and now obviously, nothing is keeping us from multiplying this with two here,

if I do it there in the result reducer,

now if I save 10, we still store 20 in the store as you can see

but now we change it at a totally different place,

we change it in the reducer.

Now as I said, this operation here might not make that much sense but you'll often have cases where you

really want to change something before you store it in the state,

you'll not always get the value you just want to pass on,

where should you then change it? In the reducer

as I show you here, you can of course also run some code before returning here, change data or in the action

creator

like I showed you before, here what I commented out.

Both works, what's better? Let's take a closer look.

In the end, the question comes down to where to put the logic, we have action creators and reducers as options. 

Now action creators as you learned are great for running async code when you dispatch an action, reducers on the other hand only are able to run synchronous code and are pure, input in updated state out. 

Reducers however keep that in mind, are meant to be the place where you update the state, this is one core redux concept. 

Action creators are not core redux concept, a core concept are actions, these javascript objects with a type and a payload. 

So the reducer is the core concept and the whole idea behind redux is that the reducer is the only thing which updates the state, action creators shouldn't prepare the state too much for that reason because it should be the reducer which does the update but there of course is also a difference between updating the state which essentially just means returning a new object which makes up our state and changing the data which goes into the state.

Still you can find arguments for both directions, I lean towards putting the logic into the reducer and not too much logic into the action creator.

Asynchronous code has to go there but once you got back the data from the server you might need to reach out, you can of course transform it in the action creator and you should do that to a certain extent but once you've got data that is relatively clean, you should hand it off to the reducer.

And if you then still need to manipulate it, for example by taking 8 times 2 or anything like that, in my

opinion that should go into the reducer.

Now you will also find arguments for the other side and in the end, it's your decision. If you choose

one approach, stick to it though, don't change it,

don't put a lot of logic in one action creator, just to then have a lot of logic in another reducer.

Be consistent and decide, where do you want to transform and prepare your data, the action creator or reducer, I recommend the latter but ultimately it's up to you, just take a consistent route.

### 9. Using Action Creators and Get State

## Section 17: 
### 1.Introduction
and learned a couple of other useful things too which I now also want to apply to our course project.
Obviously we got a whole checkout process
 
### 2. Install Redux devtools.
because I want to be able to analyze my store.

navigate away
this is not per se wrong or anything like that but we can also outsource it to action creators 
even though for synchronous action creators, it's not really neccessary but it is a consistent 



## Section 18: Adding Authentication to our Burger Project
### 1. Introduction
Welcome to this module, you learned so much about react, redux and all the core features of both libraries.

We built an amazing application with all these tools.

But one thing is missing, one thing that is not really related to react necessarily but what you have in a lot of applications, authenticating users.

And I want to show you how this would work in a react single page application, single page application because if you have a multi-page application where you render different pages for different requests from your server, you handle authentication in the traditional way of having a session on the server and returning different pages after checking the validity of the user or the authentication status on the server.

Now the special thing about authentication in react is that you have only one file and thereafter, you get no new file, so you can check the authentication status of the user on the server but not on every request, at least not in the traditional model.

So that is what we'll have a look at, how does this work in react and of course, we'll also implement authentication in our burger project.

### 2. Understanding Authentication in Single Page Applications
So how does authentication work in single page applications?

We have a server and we have our single page application running in the browser.

Now the single page application sends the authentication data to the server because we probably have a sign up or a sign in page in our SPA and therefore we get data like the e-mail address and the password and we send this to the server to validate it there because such logic obviously always has to happen on the server and this is also where we store our persistent data, in the database on the server and the server doesn't have to be firebase as in our project of course.

This can be any server, any restful API to be precise, this is what we typically communicate with when using single page applications. 

That server then send something back and you could think that's a session but since the server in a SPA world typically is a stateless restful API, we're not getting back a session because the server doesn't care about the different clients connecting to him.

Instead we get back a token, you can think of that token as a javascript object and code it as json, json web tokens are the typical form of tokens you get.

So it's a javascript object in the end you can say and this javascript object now has to be stored on the client, for example in local storage. 

We could also store it in our redux store but there, it will be lost when ever the user refreshes the page.

So we typically use local storage since that persists page refreshes and allows us to fetch that token even if the user did leave and revisit our page, so that we can leave the user are logged in if we want.

And what do we need this token for then?

Well, imagine we're making requests to some protected resource on the server, like for example we tried to change our password or we want to create a new blog post, such requests of course are only allowed to authenticated users and since we don't constantly check the authentication status on the server, we have no session there.

We pass the token along with requests to such protected resources, that token and that's important is created by the server and in a way that the server can verify if it's a valid token created by the server or not.

So that we can't fake such a token on the client, we can't create it there and send to the server, that would not work.

### 3. Required App Adjustments
We have the burger builder project and there are some things we'll adjust in this module. 

We need to add a new view, the sign up and sign in view, I'll combine it in one view where we can create new users or log users in.

We also want to protect some routes on the frontend, guard them so that for example we can't access the orders route if we're not authenticated.

And additionally, I also want to pass that token we'll receive onto the backend for requests to protect resources so that we can make sure that this does not work.

These are the adjustments we have to make on our frontend and to make them, we first of all will start with the sign up and sign in view because without having users, all the
other things are kind of hard to do.

### 4. Adding an Auth Form
So back in our application, this is where we last left it, I'll add a new container. 

I'll add in the containers folder and I'll name it auth,

you can of course name this whatever you want and there, I'll create the auth.js file and this will be this page I want to load with the sign up or sign in form. 

Now in here, I will create a class based component so I'll import react and component from react, it's been a time since we created such a component but I'm sure you still know how it works.

We create it with the class keyword, then the name of the component like auth and we extend this component we're importing.

There we need a render method where we return some jsx and in the end, I'll export this class as the file default.

Now the jsx here will be pretty close to our contact data form, I'll have a wrapping div and in there, I'll add a form element and in this form element I want to use my custom input and button components, just as I use them in the contact data component or container.

I'll also manage my form through the state of this auth container, not through redux because I'm only talking about the local state, the values the user entered into their form inputs and so on and it makes more sense to me to use them and to manage them inside the container with react's state  property.

So I'll add state here and I'll add a controls property and I'll set it up kind of equally to the contact

data so that I can reuse the logic from there,

there we had an orderForm property and then we had the various controls and they all had something like

the element, type, config and so on.

I'm going to copy the name control from there and put it into my auth controls object and rename it from

name to e-mail,

now the element type will still be an input element,

the config here I will create an input element of type e-mail and placeholder should just be mail

address, for example.

Now the value initially is empty,

regarding the rules, I want to reuse the checkValidity method from contact data and there, I support

things like required minLength, maxLength,

isEmail, isNumeric and that is basically what I want to introduce in the auth container too.

So I have required and now I also want to set up isEmail to true for this e-mail control I'm creating here,

valid initially should be false and touched is also false.

And now, I will duplicate this once to also have a password field

so here I'll add password like this, it will also be of type input

but then, the element type will be of that, the type of the input itself then will be a password and the placeholder

will therefore be password.

It should be required

and let's say we want to have a minLength of seven characters or six characters

maybe, that actually is the minLength required by firebase, of course adjust this to your backend.

With that we got this set up, we can now dynamically create that form and for that, I first of all

need to import the input and button components

so my own components there. Input from, now I need to move up into the components folder, into the UI folder

then there the input folder with the input file and the same for the button component, like this.

Now the logic is the same as in the contact data component,

there we also looped through all our controls here and I can therefore copy the code from there where

I converted my state object to an array I can loop through, I'll copy that. I'll then move over to the

auth container and add that in the render method before I return anything

and now I want to loop through it and create my form. So I'll create a new constant which I'll name

form and there, I want to take my form elements array called map to map it into an array of jsx elements,

I get each form element here and I will return jsx, I want to return my input,

it's a self-closing element and it takes a lot of keys and properties.

The first one is the key property,

there I really just want to use the form element ID which is available since I add it here.

If you remember the form's module, we added it here, it's the name of the element to be precise

and then, all the other keys which are expected. We can have a look at the contact data and we can actually

copy all the set up from there, for all the other props

we set up on the input element and add it here in the auth container.

So there we can also leave the code as it is

because I kept the name, I'm talking about a form element in my loop and I do use that here too.

I do have a config key and a value key and all these keys because I use the same set up in my state

property so that's really reusable

and with that, we now have a dynamically generated set of inputs.

Now the next thing is of course that I also need a button

so below all these inputs, I'll add a button. That button requires a button type prop which I'll set to

success, danger would be the other option we have in our application and that should not be part of my

form here though, that should be part of my form element down there where I return something and above

the button, I'll render the form content which contains my inputs.

With that, the button should not be a self-closing element but the button should allow me to add some

caption in between the tags,

so here I'll simply say submit and now we got a form with inputs and a button. To see it,

we need to load it via routing, we got the auth container and we set up all our routes in the app.js

file.

So there I want to import my auth container, import auth from ./containers auth and auth again

and now here, I'll simply replicate one of the routes and let's say for /auth, I want to load this

auth component, like that.

Let's try this out and to be able to reach that,

I'll also go into my components folder and there to navigation, navigation items into the navigation

items component,

here we got our links and I will add a new one,

I will add a link to /auth and I'll give it a caption of authenticate, something like that. With that

set up, let's go back to the application, we are on

authenticate, the styling is a bit off though

and if we inspect it, I can't spot my inputs.

So let's head back to the auth container and see where the inputs are at,

we have a form, that should be that form constant

but somehow when looping through the array

here, we seem to not really create inputs.

The reason is because I copied the code from contact data,

I'm referring to an orderForm property in my state but here in the auth container, I renamed this to controls

so I'll just rename it here too

and now if we go back, we see the controls.

Now to also give this some styling, I'll add an auth.css file and I'll copy the styling from the contact

data css file into there, replace the contact data class

here with the auth class and leave all the styling and in the auth.js file, I'll then import

my classes from the ./auth.css file and then I'll assign it to the wrapping div, so that the wrapping

div here receives the class name which is classes.Auth, this newly added css class.

If we now save all these files,

this is looking pretty good on all device sizes, I guess.

So this is my sign up form, the next step is to also configure this form to have validation,

so let's do that in the next step,

I will also copy the code for this from contact data

and by the way with all these code copying, you would correctly say can't we outsource some of this code

in some centralized file and yes we can,

we'll do this in the next module where we will apply some optimizations to this project.

For now, I would just wrap checkValidity, this method,

copy it and add it to my auth container too, so above render, I'll add checkValidity which supports various

rules,

actually all the rules I use here and now I need an inputChangedHandler and I will also get this from

contact data.

So to check the validity, I'll add a new method to my auth container, I'll name it inputChangedHandler

and there, I expect to get the event and the control name which did change

and in there, I now can use a lot of the logic but not all from the contact data.

I want to create an updated form, not named orderForm though where I update my elements but I'll

do it manually here in the auth container. So I'll create my updatedControls constant where I'll create

a new object where I'll copy this.state.controls first and then I want to only update one of the

controls, the control with the control name we have here.

So state controls simply copies all elements inside this control object

and one of them will then be overwritten by me and that's the one with the name I receive as an argument

here and that should then in turn receive a new object.

So here, I will then also call this.state.controls for that given control name and distribute all these

properties so that I can then overwrite some of the properties,

for example the value, now the value of this control and I can basically now overwrite all the properties

we have here on the control, like value and valid and touched.

So the value will now be event.target.value, valid will use this checkValidity method and there I will pass

event.target.value

and the rules of this given control,

so the rules are this.state.controls for this control name,

there we have this validation property which I'll pass,

so that is referring to that validation property each control has where I set up the rules.

So that is now what I pass as a second argument to check validity,

additionally, I'll add another property, touched, it will be set to true here whenever this inputChangedHandler

fires, the user did type something so it's definitely touched.

So with that, I update my individual control which was changed,

I update all the relevant fields I want to change.

Now I deliberately won't handle the overall form validity here,

I won't check this,

I won't disable the submit button for invalid forms because I also want to show what happens if we submit

invalid forms,

you can of course implement this too but I won't.

So I'm pretty much done here, what I will have to do is I'll call set state in inputChangedHandler

and set the controls property equal to my updatedControls

now. With that, I got this working, now I need to connect it,

I already did this because I used the same name as in contact data,

so this should work.

Now let's save this and let's see if validation is working then, back in the project if I start typing

here, it stays invalid until it's a valid email address and the password has to be at least 6 characters

long to be treated as valid.

So that's working

and as I said, the button is deliberately never changed.

So my form is finished,
