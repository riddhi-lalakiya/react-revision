# Day 5 / 30 React Revision
---


## React State and Events

The state is a built-in React object that is used to contain data or information about the component. A component’s state can change over time; whenever it changes, the component re-renders. The change in state can happen as a response to user action or system-generated events and these changes determine the behavior of the component and how it will render.  

### Coding Exercise 7: Listening to Events

Imagine you're working on a brand-new React app that should allow users to bookmark articles (e.g., news articles).

To start with your work, your task is to *"connect"* a **click event** listener to an already existing button and **output** "`Stored!`" via `console.log()`. And, of course, you should do that *"the React way"*.

#### Example Code:
##### App.js

```
import React from 'react';
import './styles.css';

// don't change the Component name "App"
export default function App() {
    return <button>Bookmark</button>;
}
```

##### styles.css

```
body {
    font-family: sans-serif;
    margin: 0;
    padding: 3rem;
    background-color: #2d2c2c;
    color: #959090;
}
```

#### Exercise Practice:

##### App.js

```
import React from 'react';
import './styles.css';

// don't change the Component name "App"
export default function App() {
    const clickHandler = () =>{
        console.log("Stored!")
    }
    return <button onClick={clickHandler}>Bookmark</button>;
}
```


### Coding Exercise 8: Working with "State"

You're working on a part of an online shop where a discounted price should be displayed on the screen once the user clicked a button.

Your task is to add an **event listener** to listen for **clicks** on the button that's already included in the `App` component.

Upon a button click, the **price should change** from `$100` to `$75`.

**Add a state value** to the existing App component function and make sure the state value is both updated upon button clicks and output as part of the JSX code.

---

Important: When using React Hooks like `useState()`, make sure to use them via `React.useState()` instead of just importing and using `useState()` standalone. This Udemy code editor / environment might fail to display the UI when not using `React.useState()`!

#### Example Code:
##### App.js

```
import React, {useState} from 'react';
import './styles.css';

// don't change the Component name "App"
// important: In this code editor, use React.useState() instead of just useState()
export default function App() {
    // const price = 100;
    
    return (
        <div>
            <p>$100</p>
            <button>Apply Discount</button>
        </div>
    );
}

```

##### styles.css

```
body {
    font-family: sans-serif;
    margin: 0;
    padding: 3rem;
    background-color: #2d2c2c;
    color: #959090;
}
```

#### Exercise Practice:

##### App.js

```
import React, {useState} from 'react';
import './styles.css';

// don't change the Component name "App"
// important: In this code editor, use React.useState() instead of just useState()
export default function App() {
    // const price = 100;
    const [price, setPrice] = React.useState(100)
    const clickHandler = () => {
        setPrice(75);
    };
    
    return (
        <div>
            <p>${price}</p>
            <button onClick={clickHandler}>Apply Discount</button>
        </div>
    );
}
```

You also find [section slides](./slides/slides.pdf).
