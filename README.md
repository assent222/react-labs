# react-labs
start learning react.js

###VS Studio shortcuts
```
ctrl + ` - show/hide terminal
ctrl + b - show/hide project tree
ctrl + p -  find file by name
F1 - show context commands
```
###What is React?

* It is JS user interface libruary
* Developed at Facebook
* For building single page applicatio
* High-speed Virtual DOM

###Setting up react tools with chrome

open https://chrome.google.com/webstore/category/apps

and add react-detector and React Developer Tools

###Start react as cdn lib

React is a simply JS viev lib, not a framework
So, you can add it in script in your html

2.1. open https://facebook.github.io/react/
2.2. add into index.html
```js
<script src="https://cdnjs.cloudflare.com/ajax/libs/react/15.3.1/react.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/react/15.3.1/react-dom.min.js"></script>
```
2.3. add into index.html
```js
ReactDOM.render(
    React.createElement('div', null, 'Hello react'),
    document.getElementById('root')
);
```


###Start JSX with babel in browser

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
```js
<script src="https://unpkg.com/babel-standalone@6/babel.min.js"></script>
//update all script tag and add attribute type="text/babel" to enable babel transpilation
<script type="text/babel">...
```



