# Day 1 / 30 React Revision
---

## What is react?
* React is a library for building user interfaces based on component.
* React can be used to develop single page, mobile, or server-rendered applications with framework.

## Why react?
* React is extremely popular.
* It makes building complex, interactive UIs a breeze.
* It's poweful and flexible.
* It has a very active and versatile ecosystem.
  
## Difference between React and Vanilla JS

| React | Vanilla Js |
| --- | --- |
| React on the other hand embracces declarative programming. | Vanilla JavaScript requires imperactive progamming. |
| It means you define the goal and React figures out how to get there. | It means you define all the steps needed to achieve a result. |

## let & const
Read more about let : [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let)

Read more about const : [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/const](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/const)

let  and const  basically replace var . You use let  instead of var  and const  instead of var  if you plan on never re-assigning this "variable" (effectively turning it into a constant therefore).

## Exports & Imports
In React projects (and actually in all modern JavaScript projects), you split your code across multiple JavaScript files - so-called modules. You do this, to keep each file/ module focused and manageable.

To still access functionality in another file, you need `export`  (to make it available) and `import`  (to get access) statements.

You got two different types of exports: **default** (unnamed) and **named** exports:

**default** => `export default ...;`

**named** => `export const someData = ...;`

You can import **default exports** like this:
`import someNameOfYourChoice from './path/to/file.js';`
Surprisingly, `someNameOfYourChoice` is totally up to you.

**Named exports** have to be imported by their name:
`import { someData } from './path/to/file.js';`

A file can only contain one default and an unlimited amount of named exports. You can also mix the one default with any amount of named exports in one and the same file.

When importing **named exports**, you can also import all named exports at once with the following syntax:

`import * as upToYou from './path/to/file.js';`

`upToYou` is - well - up to you and simply bundles all exported variables/functions in one JavaScript object. For example, if you `export const someData = ...` (`/path/to/file.js`) you can access it on `upToYou` like this: `upToYou.someData`.

### Coding Exercise 1: Working with Functions
Your task is to write a new function that should be named combine and have the following characteristics:

* Accept three input values
* Calculate a new value based on the three input values: a * b / c (if a, b & c are the input values)
* Return the calculated result

#### Example Code:
```
function combine() {
    return a * b / c;
}
```

#### Exercise Practice:
```
function combine(a, b, c) {
    return a * b / c;
}
console.log(result(2, 3, 5))
```


You also find [section slides](./slides/slides.pdf).