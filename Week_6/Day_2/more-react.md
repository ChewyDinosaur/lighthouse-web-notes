# More ReactJS

We started off with some conceptual stuff about **React** as a framework for building Web Components.

Using the example of an anchor tag (`<a href="https://lighthouselabs.ca" title="Lighthouse Labs">Lighthouse</a>`), we discussed how this is a built-in HTML tag with a prescribed appearance and behaviour. But that the attributes on the <a> tag are analogous to props in a React component, and that we could build one ourselves if we wanted to.

For example: `<Anchor href="https://lighthouselabs.ca" title="Lighthouse Labs" linkText="Lighthouse" />`

If we just did `$("<Anchor>")` with jQuery, we would get a <div> with no additional behaviours. And the code we would write in jQuery to add all of the click and hover behaviours to the element wouldn't a) be part of the "definition" of that component and b) wouldn't be as portable as a React component is.

I introduced [Web Components](https://developer.mozilla.org/en-US/docs/Web/Web_Components) as a technology that is upcoming and that React is reminiscent of.

FOUC - Flash of Unstyled Content

The image we looked through to learn about Lifecycle methods can be found [here.](https://i.imgur.com/Kiec7S6.png)

## State vs Props

Props always come in from outside the component, intended to be read-only.

You CAN set default props, but they're still read-only.

State is always and only inside the component.

State IS mutable. BUT ONLY WITH `this.setState()`.

**Never**, ever, ever, never, ever, even if you think it's a good idea, **EVER** write to state directly.

We took a stab at implementing some of the <Anchor> component behaviour:
```javascript
import React, { Component } from 'react';

class Anchor extends Component {
  constructor(props) {
    super(props);

    this.state = {
      clickCount: 0
    }

    this.goToLink = this.goToLink.bind(this);
  }

  pointerCursor(e) {
    e.target.style.cursor = "pointer";
  }

  defaultCursor(e) {
    e.target.style.cursor = "normal";
  }

  goToLink() {
    this.setState({clickCount: this.state.clickCount + 1});
    window.location.href = this.props.href;
  }

  render() {
    return (
      <span onClick={this.goToLink} onMouseOver={this.pointerCursor} onMouseOut={this.defaultCursor} style={{color: blue; textDecoration: underline;}}>{this.props.linkText}</span>
    )
  }
}
```