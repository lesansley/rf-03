# rf-03

Running JSX in the browser

By adding Babel to the page we can run JSX directly from the browser.

Add the [babel](https://unpkg.com/@babel/standalone@7.12.4/babel.js) script to the page.

Identify the `script` tag in which JSX is being written as being `type="text/babel"`
The browser ignores the `script` tag but Babel recognises that it's a type `text/babel` and takes the contents of that script tag and compiles it into javascript. The compiled code is then added to a new `script` tag, which the browser evaluates.

## JSX code
```
const rootElement = document.getElementById('root')
const className = 'container'
const id = 'greeting'
const helloText = 'hello'
const worldText = 'world'
const message = `${helloText} ${worldText}`
const props = {className, id, children: message}
const element = <div {...props} />
ReactDOM.createRoot(rootElement).render(element)
```

## Compiled code
```
"use strict";

var rootElement = document.getElementById('root');
var className = 'container';
var id = 'greeting';
var helloText = 'hello';
var worldText = 'world';
var message = "".concat(helloText, " ").concat(worldText);
var props = {
  className: className,
  id: id,
  children: message
};
var element = /*#__PURE__*/React.createElement("div", props);
ReactDOM.createRoot(rootElement).render(element);
```
