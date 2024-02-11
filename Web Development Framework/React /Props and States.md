
# Understanding Props and State in React

React components use `props` and `state` to handle data and render dynamic content. 

## Props

`Props` are used to pass data from parent to child components at the time of calling the child component. They are read-only and cannot be modified by the child components.

### Example of using Props:

**Greeting.js** - A child component that receives `props`:
```javascript
import React from 'react';

const Greeting = (props) => {
  return <h1>Hello, {props.name}!</h1>;
}

export default Greeting;
```

**App.js** - The parent component passing `props` to the child:
```javascript
import React from 'react';
import Greeting from './Greeting';

const App = () => {
  return (
    <div>
      <Greeting name="Alice" />
    </div>
  );
}

export default App;
```

## State

`State` is a mutable object that is used to hold data that may change over time. Changes in state trigger re-renders of the component.

### Example of using State:

**Counter.js** - A component with its own `state`:
```javascript
import React, { useState } from 'react';

const Counter = () => {
  const [count, setCount] = useState(0);

  const incrementCount = () => {
    setCount(count + 1);
  };

  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={incrementCount}>
        Click me
      </button>
    </div>
  );
}

export default Counter;
```

**App.js** - Using the `Counter` component inside the parent `App` component:
```javascript
import React from 'react';
import Counter from './Counter';

const App = () => {
  return (
    <div>
      <Counter />
    </div>
  );
}

export default App;
```

By using `props` and `state`, React allows you to create interactive and dynamic user interfaces efficiently.

