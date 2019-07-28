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
