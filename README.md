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
