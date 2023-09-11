# Sophilabs-Assesments
REACT.js
Finish

1 Which of the following is NOT a good reason for having presentational and container logic separate in a component?

a Readability

b Testability

c Shorter code overall

d Separating responsibilities

C
-------------------

2 You are calling a lazy component inside your App component. You must ensure that your web page displays a fallback user interface in case the lazy component fails to load because of a network error. How would you apply an error boundary inside App?

1 I don't know yet.

2 import React, { Suspense } from 'react';  
import ErrBoundary from './ErrBoundary';  

const LazyComp = React.lazy(() => import('./LazyComp'));  

const App = () => (  
  <>      
    <Suspense fallback={<ErrBoundary />}>            
        <LazyComp />  
    </Suspense>  
  </>  
);
import React, { Suspense } from 'react';  
import ErrBoundary from './ErrBoundary';  

const LazyComp = React.lazy(() => import('./LazyComp'));  

const App = () => (  
  <>  
    <ErrBoundary>  
      <Suspense fallback={<>...</>}>  
          <LazyComp />  
      </Suspense>  
    </ErrBoundary>  
  </>  
);
import React, { Suspense } from 'react';  
import ErrBoundary from './ErrBoundary';  

const LazyComp = React.lazy(() => import('./LazyComp'));  

const App = () => (  
  <>      
    <Suspense fallback={<>...</>}>  
        <ErrBoundary />  
        <LazyComp />  
    </Suspense>  
  </>  
);
import React, { Suspense } from 'react';  

const LazyComp = React.lazy(() => import('./LazyComp'));  
const ErrBoundary = React.lazy(() => import('./ErrBoundary'));  

const App = () => (  
  <>      
    <Suspense fallback={<ErrBoundary />}>  
        <ErrBoundary />  
        <LazyComp />  
    </Suspense>  
  </>  
);


The correct answer is:

import React, { Suspense } from 'react';
import ErrBoundary from './ErrBoundary';
const LazyComp = React.lazy(() => import('./LazyComp'));

const App = () => (
  <>
    <Suspense fallback={<ErrBoundary />}>
      <LazyComp />
    </Suspense>
  </>
);

----------------------

You are calling a lazy component inside your App component. You must ensure that your web page displays a fallback user interface in case the lazy component fails to load because of a network error. How would you apply an error boundary inside App?

1 I don't know yet.

2 import React, { Suspense } from 'react';  
import ErrBoundary from './ErrBoundary';  

const LazyComp = React.lazy(() => import('./LazyComp'));  

const App = () => (  
  <>      
    <Suspense fallback={<ErrBoundary />}>            
        <LazyComp />  
    </Suspense>  
  </>  
);

3 import React, { Suspense } from 'react';  
import ErrBoundary from './ErrBoundary';  

const LazyComp = React.lazy(() => import('./LazyComp'));  

const App = () => (  
  <>  
    <ErrBoundary>  
      <Suspense fallback={<>...</>}>  
          <LazyComp />  
      </Suspense>  
    </ErrBoundary>  
  </>  
);

4 import React, { Suspense } from 'react';  
import ErrBoundary from './ErrBoundary';  

const LazyComp = React.lazy(() => import('./LazyComp'));  

const App = () => (  
  <>      
    <Suspense fallback={<>...</>}>  
        <ErrBoundary />  
        <LazyComp />  
    </Suspense>  
  </>  
);

5 import React, { Suspense } from 'react';  

const LazyComp = React.lazy(() => import('./LazyComp'));  
const ErrBoundary = React.lazy(() => import('./ErrBoundary'));  

const App = () => (  
  <>      
    <Suspense fallback={<ErrBoundary />}>  
        <ErrBoundary />  
        <LazyComp />  
    </Suspense>  
  </>  
);

the correct answer

import React, { Suspense } from 'react';
import ErrBoundary from './ErrBoundary';
const LazyComp = React.lazy(() => import('./LazyComp'));

const App = () => (
  <>
    <Suspense fallback={<ErrBoundary />}>
      <LazyComp />
    </Suspense>
  </>
);

-----------------------

A statement uses a synthetic event:

<button onClick={(e) => this.createCaption(id, e)}> Create a caption </button>
You must replicate this behavior without using the synthetic event explicitly. To do so, you run:

<button onClick={(flag) => this.createCaption(id, flag)}> Create a caption </button>
The above command produces no error but still uses an event explicitly. How can you write a command that does not produce an error and does not use an event explicitly?

1 I don't know yet.
2 <button onClick={this.createCaption.bind(this, id)}> Create a caption </button>
3 <button onClick={{e} => this.createCaption.bind(e, this, id)}> Create a caption </button>
4 <button onClick={{e} => this.createCaption.concat(e, this, id)}> Create a caption </button>
5 <button onClick={this.createCaption.concat(this, id)}> Create a caption </button>

The correct answer is:

<button onClick={this.createCaption.bind(this, id)}> Create a caption </button>

--------------------

How can a component subscribe to a partial state out of an external state container?

1 By using component props.

2 By using an HOC that receives the list of state elements needed.

3 By using pure components.

4 By using function components.

The correct answer is:

2 By using an HOC that receives the list of state elements needed.

-------------------

You are tasked with wrapping an existing jQuery component as a React component.
You know that you can create the correct HTML through your React component, but you need to target one of the elements created by your React component with jQuery.

How can you find an element created by your React component in the DOM, so that you can target it with jQuery?

1 By letting the React component output dynamic JavaScript code that targets the correct part of the DOM.

2 This is not possible with React, the DOM cannot be accessed by anything other than the component itself.

3 By ensuring that the component output to the DOM has unique attributes which could be targeted by jQuery.

4 By using the low level ReactDOM.findDomNode method and passing in your component.

The correct answer is:

3 By ensuring that the component output to the DOM has unique attributes which could be targeted by jQuery.

------------------

What's the right syntax to define a class field function?

1 functionName() {};
2 functionName = () {};
3 this.funcName = () => {}
4 funcName = () => {};

The correct answer is:

1 functionName = () {};

------------------

Based on your state, your component returns the following JSX:

<div>
   <div>Hello</div>
</div>
The underlying state gets updated, and your component renders the following

<div>
   <div class="red">Hello</div>
</div>
What changes did React make to the DOM to render the updated component to the DOM?

1 React replaced the DOM elements from the root of the component's representation (the outer DIV).

2 Because you returned changed JSX, React removed the existing DOM elements and rendered from scratch.

3 React selectively added the class attribute to the inner DIV.

4 Because only the inner DV was updated, the outer DIV was left alone and only the inner DIV was replaced.

The correct answer is:

3 React selectively added the class attribute to the inner DIV.

-------------------

What's the point of having a React.Children utility?

1 To deal with the this.props.children opaque data structure.

2 To work on both the content and attributes of a DOM element.

3 To provide a faster way to iterate over DOM nodes.

4 To enhance the readability of code written to work with a component's children.

The correct answer is:

1 To deal with the this.props.children opaque data structure.

-----------------

What is the correct syntax to use this component with the ReactDOM.render() method?

function Greeting(props) { 
 return <h1>Greetings New User</h1>;
}

1 ReactDOM.render(, document.getElementById('root'));

2 ReactDOM.render(document.getElementById('root'), <Greeting />);

3 ReactDOM.render(<Greeting />, document.getElementById('root'));

4 ReactDOM.render(document.getElementById('root'), <greeting />);

The correct answer is:

3 ReactDOM.render(<Greeting />, document.getElementById('root'));

-----------------

For a React app that represents static data, where do data elements go?

1 In the context

2 In the state of the various components

3 In the props of the various components

The correct answer is:

2 For a React app that represents static data, the data elements typically go in the props of the various components.

----------------

How do you define a React pure component?

1 extends React.PureComponent

2 All function components are Pure Components.

3 extends React.Component(Pure)

4 class PureComponent {}

The correct answer is:

3 extends React.PureComponent

---------------

Is JSX required to work in React?

No, you can use plain JavaScript instead.

No, but it's recommended for the best performance.

Yes.

No, you can use YAML instead.

It's only required if you're using react-dom.

the correct answer is:

No, JSX is not required to work in React.

--------------

What is a good indicator that you're using the correct React production build?

1 The build is smaller in size.

2 No warning from React about it.

3 The build is minified.

The correct answer is:

No warning from React about it.

-------------

In your component you have a controlled input, with its value coming from state and being updated on state when the user changes the input value.
You want it to have a default value which can be changed by the user.

What do you need to do?

1 Just set the value attribute, React will allow the user to update it.

2 You can't set a default value for an input without using setState.

3 Use a ref so that you can dynamically set the value on the underlying DOM element.

4 Use the defaultValue attribute, it will ensure that the value has a default but can still be overriden.

The correct answer is:

Use the defaultValue attribute, it will ensure that the value has a default but can still be overridden.

-----------

What is shallow rendering?

1 Rendering the component without needing to pass any props or setting any state.

2 Rendering the component without enforcing the prop types.

3 Rendering the component with a shallow context object.

4 Rendering just the component and not its children.

The correct answer is:

Rendering just the component and not its children.

-----------

When working with a data tree, what can you do to improve on components responsibilities?

Make every component receives a single object from the data tree.

Make every component render only a single child component.

Match the data hierarchy to the components hierarchy.

The correct answer is:

Match the data hierarchy to the components hierarchy.

-----------

Which case would you use to name a React event?

I don't know yet.

Camel case

Lower case

Upper case

Alphanumeric case

the correct answer is: 

When naming a React event, you would typically use camel case.

----------

Which components can be shallow-rendered?

Only function components

All components

Only class components

the correct answer is:

All components, both function components and class components, can be shallow-rendered.

-----------

Which components can be shallow-rendered?

1 Only function components

2 All components

3 Only class components

The correct answer is:

All components

------------

SX renders the following element:

<a href="/about" onClick={navHandler}>About</a>
When a user clicks the "About" link, React must change the URL to be /about without doing a full page refresh. Which event method do the navHandler functions need to include?

1 I don't know yet.

2 event.cancelDefault()

3 event.preventDefault()

4 event.stopPropagation()

5 event.cancelPropagation()

The correct answer is:

event.preventDefault()

-------------

Which statement decides the logic of a component based on several cases?

1 I don't know yet.

2 case

3 goto

4 switch

5 try/except

The correct answer is:

switch

-----------*--

Which package holds the useState hook?

1 I don't know yet.
2 reactServer
3 reactDOM
4 reactClient
5 react 

The correct answer is:

react

-----------------

You have a div inside a component Foo that accepts a variable customP as follows: 

function Foo() {  
  return <div style={customP}>This is a sample text.</div>;  
}
How would you define customP with a width of 100 pixels, height of 100 pixels, and a green background color?

1 I don't know yet.

2 const customP = {  
  width: 100,  
  height: 100,  
  backgroundColor: 'green'  
};
3 const customP = {  
  'width': '100',  
  'height': '100',  
  'backgroundColor': 'green'  
};
4 const customP = {  
  Width: 100,  
  Height: 100,  
  BackgroundColor: 'green'  
};
5 const customP = {  
  .width: 100,  
  .height: 100,  
  .backgroundColor: 'green'  
};

The correct answer is:

const customP = {
width: 100,
height: 100,
backgroundColor: 'green'
};
Explanation: In JavaScript object literals (like the style object), property names are usually written without quotes, and their values can be numbers, strings, or other valid data types. So, the correct syntax for defining customP with the specified properties would be without quotes and with numeric values for width and height. Additionally, the color value should be specified as a string, as in the correct answer.

--------------------

A component, Foo, accepts one argument from a user. How can you rewrite the component Foo to make it less verbose? 

function Foo(props) {  
const g = {props.itemNo}  
return <div> Item number: g</div>  
}  

function App() {    
return <Foo itemNo={70}/> ;  
}
I don't know yet.

function Foo(props) {  
return <> Item number: props.itemNo</>  
}
function Foo(props) {  
return <div> Item number: props.itemNo</div>  
}
function Foo(props) {  
return <div> Item number: {props.itemNo}</div>  
}
function Foo(props) {  
const g = props.itemNo  
return <div> Item number: g</div>  
}

The correct answer is:

function Foo(props) {
return <div> Item number: {props.itemNo}</div>
}

-+--------------

Which lifecycle methods can be used with stateless function components?

Just componentWillMount and componentDidMount

None

All of them

Stateless functional components (SFCs) don't have lifecycle methods. So, the correct answer is:

None

--------------------

Final - End
