# Intro to ReactJS

## Intro to Frameworks

Frameworks are a subset of libraries with:

* Opinions
* Abstractions

### Express

#### Opinions

* What do you want to make? Web Servers
* We prefer X over Y
  * We prefer minimalism & speed over built-in functionality
  * Standard HTTP Behaviour over adding too many specific behaviours

#### Abstractions

* router
* route
* request
* response
* middleware - everything you write in express is middleware.

## Judging React as a Framework

### Opinions of React

[React](https://reactjs.org/)

* What do you want to make? Dynamic User Interface

### Declarative-First

Rather than focus on executing commands, we are constructing expressions

```javascript
// Imperative code
if(someCondition){
  doX();
} else {
  doY();
}

// Declarative
const result = someCondition ? x : y;

// Imperative
for(const item of items){
  doSomething(item);
}

// Declarative
const results = items.map(item => transform(item))
```

### Component Hierarchy

The component hierarchy in HTML is a tree.

* We have strict separation of which code is changing which DOM. With components, we can include with a given section of DOM all the code that may alter that DOM.
* We can easily work on different parts of the app at different times.
* We have the JSX language, so we can drop our HTML directly into our JS (with some changes maybe.)

### Learn Once, Write Anywhere

React, itself, is independent of the DOM. There is a separate ReactDOM library that is doing kind of a lot, but React itself is just a reconciliation system. All it does is takes two tree structures, compare them, and figure out how little it has to do to make changes. This make it an ideal general framework that can be applied to:

* HTML DOM
* Native
* Audio libraries
* Canvas
* ART and SVG

### State Management & Presentation

There are two types of code you will write in most React Apps:

* State Management
* Presentation

Tweeter had imperative DOM management, and no state management. In React per se, we have imperative state management and declarative DOM management. So, we are writing code that:

* Imperatively updates state
* Given a certain state, renders a certain presentation

## JSX

JSX is a convenience language that we don't exactly neeeeeed, but helps us be more effective.
```
const jsxExpr = (<p className='greeting'>Hello, <strong>World</strong></p>);
```
becomes
```
"use strict";
var jsxExpr = React.createElement(
  "p",
  { className: "greeting" },
  "Hello, ",
  React.createElement("strong", null, "World")
);
```

### JSX Demos

[Gist](https://gist.github.com/JoelCodes/9ff5efa051d81b650993311456b1d35f)