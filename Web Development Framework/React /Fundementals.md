
# Fundamentals of React

React's popularity stems from its simplicity and the power it gives developers to craft modern, reactive user interfaces. At its core, React is all about components.

## Components
Components are the heart of React's powerful, declarative programming model. React encourages the building of reusable UI segments, which can be independently created, maintained, and manipulated.

### Types of Components in React:

#### 1. Functional Component
- These are JavaScript functions that accept `props` as an argument and return React elements.
- They do not hold or manage state (unless using hooks).
- Functional components do not have lifecycle methods.

**Example of a Functional Component:**
```javascript
import React from 'react';

function App() {
  return (
    <div>
      <h1>Hello folks</h1>
    </div>
  );
}
```

#### 2. Class Component
- Class components are more complex than functional components.
- They can hold and manage state and have lifecycle methods.
- Class components must have a `render()` method that returns HTML.

**Example of a Class Component:**
```javascript
import React, { Component } from 'react';
import ReactDOM from 'react-dom';

class App extends Component {
  render() {
    return (
      <div>
        <h1>Hello folks</h1>
      </div>
    );
  }
}

ReactDOM.render(<App />, document.getElementById('root'));
```

### Note on Class Components:
While class components have been the backbone of React for a long time, the introduction of hooks in React 16.8 allows functional components to manage state and side effects, making class components less common in modern React development.
```
