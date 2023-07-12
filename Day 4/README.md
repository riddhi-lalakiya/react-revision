# Day 4 / 30 React Revision
---


## The concept of "Composition" ("children props")

children is a special prop, automatically passed to every component, that can be used to render the content included between the opening and closing tags when invoking a component.

The concept of children props ( written as {props.children}) is far less twisted than it sounds when placed within the context of React.js code. The { props.children } property allows you to create a generic template component that can be modified by the parent when it is invoked. This means that a parent component can pass whatever is needed in the child component, even generated layout features that can then be rendered by the child.

### Coding Exercise 6: Component Composition

You are working on a UI prototype for a "Todos" application. At the moment, the prototype displays some basic todos for learning React and a short info message.

![exercise component composition](./img/exercise%20component%20composition.png)

Your task is to **optimize the code** and use React **component composition** to create a re-usable `<Card />` component that can be wrapped around different content (e.g., todo markup, info message markup).

The final UI should look like the initial UI - i.e., no styling changes are required. But the code should change and **embraces React's composability**.

Create the `<Card />` component in the already existing `Card.js` file and use a `<div>` as a main element in that component.

#### Example Code:
##### App.js

```
import './styles.css';

// don't change the Component name "App"
export default function App() {
    return (
        <div>
            <h1>Todos</h1>
            <div className="card>
              <p>Please note: Below are just the most important todos - feel free to add more.</p>
            </div>
            <ul>
              <li className="todo">
                <div className="card>
                  <h2>Learn React</h2>
                  <p>Learn React fundamentals & explore core concepts</p>
                </div>
              </li>
              <li className="todo">
                <div className="card">
                  <h2>Practice React</h2>
                  <p>Apply your knowledge & build demo projects</p>
                </div>
              </li>
            </ul>
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

ul {
    list-style: none;
    margin: 2rem 0;
    padding: 0;
}

li {
    margin: 1rem 0;
}

.card {
    padding: 1rem;
    background-color: #1d1c2c;
    border-radius: 6px;
    box-shadow: 0 2px 4px rgba(0,0,0,0.2);
}

.todo h2 {
    margin: 0;
    text-transform: uppercase;
    font-size: 1.25rem;
    color: #eee;
}

.todo p {
    margin: 0.5rem 0 0 0;
    color: #999;
}
```

##### Card.js

```
empty file
```

#### Exercise Practice:

##### App.js

```
import './styles.css';
import Card from './Card'; // <-- import component

// don't change the Component name "App"
export default function App() {
    return (
        <div>
            <h1>Todos</h1>
            <Card> // <-- Replace HTML element
              <p>Please note: Below are just the most important todos - feel free to add more.</p>
            </Card>
            <ul>
              <li className="todo">
                <Card> // <-- Replace HTML element
                  <h2>Learn React</h2>
                  <p>Learn React fundamentals & explore core concepts</p>
                </Card>
              </li>
              <li className="todo">
                <Card> // <-- Replace HTML element
                  <h2>Practice React</h2>
                  <p>Apply your knowledge & build demo projects</p>
                </Card>
              </li>
            </ul>
        </div>
    );
}
```

##### Card.js

```
import React from 'react'

function Card(props){
    return(
        <div className="card">{props.children}</div>
        )
}

export default Card;
```

## Quiz 1: Learning Check: React Basics, Components, Props & JSX

1. Which kind of code do you write when using React.js?
    * Definitive JSX Code
    * Imperative JavaScript Code
    * Declarative JavaScript Code

**Ans:** Declarative JavaScript Code

2. What is "JSX"?
    * It's a standard JavaScript syntax
    * It's a special, non-standard syntax which is enabled in React projects
    * It's a special string which you can pass to React functions

**Ans:** Declarative JavaScript Code

3. Why is React all about "Components"?
    * Every UI in the end up is made up of multiple building blocks (= components), hence it makes sense to think about user interfaces as "combinations of components"
    * React projects are configured to only work with components, hence you have to use them when writing React code.
    * Components offer better performance than "standard user interfaces" that don't use components.

**Ans:** Every UI in the end up is made up of multiple building blocks (= components), hence it makes sense to think about user interfaces as "combinations of components"

4. What does "declarative" mean?
    * "Declarative" is the same as "imperative"
    * You define the individual steps that need to be taken to achieve a desired outcome (e.g. a target UI).
    * You define the desired outcome (e.g. a target UI) and let the library (React) figure out the steps.

**Ans:** You define the desired outcome (e.g. a target UI) and let the library (React) figure out the steps.

5. What is a "React Component"?
    * It's a JavaScript function which typically returns HTML (JSX) code that should be displayed.
    * It's a replacement for standard HTML which is supported by modern browsers.
    * It's a JavaScript function that must not return anything.

**Ans:** It's a JavaScript function which typically returns HTML (JSX) code that should be displayed.

6. How many custom React components must a React app have?
    * At least 2
    * At most 99
    * That's totally up to you

**Ans:** That's totally up to you

7. Which statement is correct?
    * With React, you build multiple sibling component trees that are then mounted into the same DOM node.
    * With React, you build a component tree with one root component that's mounted into a DOM node.
    * With React, you always mount every component into it's own DOM node.

**Ans:** With React, you build a component tree with one root component that's mounted into a DOM node.

8. What does "component tree" mean?
    * It means that you have a root node which then has more components nested beneath it.
    * It means that you must always return more than one component or HTML element per component function.
    * It means that you can build multiple components.

**Ans:** It means that you have a root node which then has more components nested beneath it.

9. How do you pass data between components?
    * Via global JavaScript variables that are accessible in all files
    * Via "custom HTML attributes" (better known as "props")
    * Via standard HTML attributes which you can use in non-React apps as well

**Ans:** Via "custom HTML attributes" (better known as "props")

10. How can you output dynamic data in React components (i.e. in the returned JSX code)?
    * You can use single curly braces (opening & closing) with any JS expression between them.
    * React has a special syntax that allows you to output variable values (i.e. values stored in variables) and nothing else: Opening & closing curly braces
    * You can't

**Ans:** You can use single curly braces (opening & closing) with any JS expression between them.

Source Code - [Click Here](./code/the-concept-of-composition/)
