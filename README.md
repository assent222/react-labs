# react-labs
start learning react.js

### VS Studio shortcuts
```
ctrl + ` - show/hide terminal
ctrl + b - show/hide project tree
ctrl + p -  find file by name
F1 - show context commands
```

### GIT tips
```
//untrack file
git rm --cached filename
git update-index --no-assume-unchanged filename
//clear commits etc
git gc --prune=now
```

### What is React?

* It is JS user interface libruary
* Developed at Facebook
* For building single page applicatio
* High-speed Virtual DOM

### Setting up react tools with chrome

open https://chrome.google.com/webstore/category/apps

and add react-detector and React Developer Tools

### Start react as cdn lib

React is a simply JS viev lib, not a framework
So, you can add it in script in your html

2.1. open https://facebook.github.io/react/
2.2. add into index.html
```
<script src="https://cdnjs.cloudflare.com/ajax/libs/react/15.3.1/react.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/react/15.3.1/react-dom.min.js"></script>
```
2.3. add into index.html
```
ReactDOM.render(
    React.createElement('div', null, 'Hello react'),
    document.getElementById('root')
);
```


### Start JSX with babel in browser

* JSX - syntax to write render function which doesn`t compatible with native JS. It calls JavaScript with XML.
* Babel - Transpiles JSX and ES6 to JS ES5 code

```
<div>Hello world</div>

||
|| BABEL
\/

React.createElement('div', null, 'Hello world');

```

3.1 add inbrowser babel transpiler

* see https://babeljs.io/ -> docks
* see https://github.com/babel/babel-standalone#usage


add into index.html
```
//add due to babel throw Invalid regular expression
//to apply it on the page press ctrl + F5
<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
//add inbrowser babel
<script src="https://unpkg.com/babel-standalone@6/babel.min.js"></script>
//update all script tag and add attribute type="text/babel" to enable babel transpilation
<script type="text/babel">...
```

### React Component

4.1. What is a react component?

When we're thinking about React applications, we should be thinking about a collection of components. 

Components are small user interface elements that display data as it changes over time. These components can be composed together, nested inside of one another to create entire interfaces. Check Nordstrom.com. Nordstrom uses a lot of React, as we can see in the React Detector.

4.2. Create a react component ECMA5

```js
//1. Always use a capital letter to name component in your code
//2. createClass function should always be called with obj which contains render function
var MyComponent = React.createClass({
            render() { //3. that create field "render" and set render() function into object
                //4. return should be in one line with container tag like <div>, in case of different lines react will throw error
                //return
                //<div> ... </div> <- ERROR
                //but you can use ()
                //return (
                //  <div> ... </div> <- GOOD
                //)
                return <div> 
                        <h1>Hello, world!</h1>
                        <p>This is my first react component</p>
                    </div>
                
            }
        });

        ReactDOM.render(
            <MyComponent />,
            document.getElementById('root')
        );
```

4.3. Create a react component ECMA6
```js
class MyComponentES6 extends React.Component {
    render() {
        return <div>
            <h1>Hello, component ES6!</h1>
            <p>This is my first react component</p>
        </div>
    }
}
```

4.3. Create a react component ECMA6 Stateless
```js
const MyComponentStateless = () => {
    return <div>
        <h1>Hello, component ES6 Stateless!</h1>
        <p>This is my first react component</p>
    </div>
};
```

### Props

Components let you split the UI into independent, reusable pieces, and think about each piece in isolation.

Conceptually, components are like JavaScript functions. They accept arbitrary inputs (called "props") and return React elements describing what should appear on the screen.

5.1. add header property
```js
    class MyComponentES6 extends React.Component {
        //view property using JSQ expression {...}
        render() {
            return <div>
                <h1>{this.props.header}</h1>
                <p>This is my first react component</p>
            </div>
        }
    }

    ReactDOM.render(
            //set properties
            <div>
                <MyComponentES6 header="Hello, component ES6!"/>
            </div>,
        document.getElementById('root')
    )
```

5.2. use props.children using self-closing tag
```js
    class MyComponentES6 extends React.Component {
        //view property using JSQ expression {...}
        render() {
            return <div>
                <h1>{this.props.header}</h1>
                <p>{this.props.children}</p>
            </div>
        }
    }

    ReactDOM.render(
            //set properties as attribute and as chield using self-closing tag
            <div>
                <MyComponentES6 header="Hello, properties! This is header">
                    This is my children property
                </MyComponentES6>
            </div>,
        document.getElementById('root')
    )
```