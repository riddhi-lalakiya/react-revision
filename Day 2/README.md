# Day 2 / 30 React Revision
---

## Arrow Functions
* Read more: [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions)
* Arrow functions are a different way of creating functions in JavaScript. Besides a shorter syntax, they offer advantages when it comes to keeping the scope of the this  keyword ([see here](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this#description)).

Arrow function syntax may look strange but it's actually simple.
```
function callMe(name) { 
    console.log(name);
}
```
which you could also write as:
```
const callMe = function(name) { 
    console.log(name);
}
```
becomes:
```
const callMe = (name) => { 
    console.log(name);
}
```

### Important:
When having **no arguments**, you have to use empty parentheses in the function declaration:
```
const callMe = () => { 
    console.log('Max!');
}
```
When having **exactly one argument**, you may omit the parentheses:
```
const callMe = name => { 
    console.log(name);
}
```
When **just returning a value**, you can use the following shortcut:
```
const returnMe = name => name
```
That's equal to:
```
const returnMe = name => { 
    return name;
}
```

## Classes
Classes are a feature which basically replace constructor functions and prototypes. You can define blueprints for JavaScript objects with them.

Like this:
```
class Person {
    constructor () {
        this.name = 'Riddhi Lalakiya';
    }
}
 
const person = new Person();
console.log(person.name); // prints 'Riddhi Lalakiya'
```

In the above example, not only the class but also a property of that class (=> `name`) is defined. The syntax you see there, is the "old" syntax for defining properties. In modern JavaScript projects (as the one used in this course), you can use the following, more convenient way of defining class properties:
```
class Person {
    name = 'Riddhi Lalakiya';
}
 
const person = new Person();
console.log(person.name); // prints 'Riddhi Lalakiya'
```

You can also define methods. Either like this:
```
class Person {
    name = 'Max';
    printMyName () {
        console.log(this.name); // this is required to refer to the class!
    }
}
 
const person = new Person();
person.printMyName();
```

Or like this:
```
class Person {
    name = 'Max';
    printMyName = () => {
        console.log(this.name);
    }
}
 
const person = new Person();
person.printMyName();
```

The second approach has the same advantage as all arrow functions have: The `this` keyword doesn't change its reference.

You can also use **inheritance** when using classes:
```
class Human {
    species = 'human';
}
 
class Person extends Human {
    name = 'Riddhi Lalakiya';
    printMyName = () => {
        console.log(this.name);
    }
}
 
const person = new Person();
person.printMyName();
console.log(person.species); // prints 'human'
```

## Array Methods
Not really next-gen JavaScript, but also important: JavaScript array functions like `map()`, `filter()`, `reduce()` etc.

You'll see me use them quite a bit since a lot of React concepts rely on working with arrays (in immutable ways).

The following page gives a good overview over the various methods you can use on the array prototype - feel free to click through them and refresh your knowledge as required: [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)

Particularly important in this course are:

`map()` => [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map)

`find()` => [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/find](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/find)

`findIndex()` => [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/findIndex](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/findIndex)

`filter()` => [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter)

`reduce()` => [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/Reduce?v=b](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/Reduce?v=b)

`concat()` => [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/concat?v=b](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/concat?v=b)

`slice()` => [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/slice](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/slice)

`splice()` => [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/splice](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/splice)

## Spread & Rest Operator
The spread and rest operators actually use the same syntax: `...`

Yes, that is the operator - just three dots. It's usage determines whether you're using it as the spread or rest operator.

### Using the Spread Operator:

The spread operator allows you to pull elements out of an array (=> split the array into a list of its elements) or pull the properties out of an object. Here are two examples:

```
const oldArray = [1, 2, 3];
const newArray = [...oldArray, 4, 5]; // This now is [1, 2, 3, 4, 5];
```

Here's the spread operator used on an object:
```
const oldObject = {
    name: 'Riddhi Lalakiya'
};
const newObject = {
    ...oldObject,
    age: 27
};
```

`newObject` would then be
```
{
    name: 'Riddhi Lalakiya',
    age: 27
}
```

The spread operator is extremely useful for cloning arrays and objects. Since both are [reference types (and not primitives)](https://www.youtube.com/watch?v=9ooYYRLdg_g&feature=youtu.be), copying them safely (i.e. preventing future mutation of the copied original) can be tricky. With the spread operator you have an easy way of creating a (shallow!) clone of the object or array.

## Destructuring
Destructuring allows you to easily access the values of arrays or objects and assign them to variables.

Here's an example for an array:
```
const array = [1, 2, 3];
const [a, b] = array;
console.log(a); // prints 1
console.log(b); // prints 2
console.log(array); // prints [1, 2, 3]
```

And here for an object:
```
const myObj = {
    name: 'Riddhi Lalakiya',
    age: 27
}
const {name} = myObj;
console.log(name); // prints 'Riddhi Lalakiya'
console.log(age); // prints undefined
console.log(myObj); // prints {name: 'Riddhi Lalakiya', age: 27}
```

Destructuring is very useful when working with function arguments. Consider this example:
```
const printName = (personObj) => {
    console.log(personObj.name);
}
printName({name: 'Riddhi Lalakiya', age: 27}); // prints 'Max'
```

Here, we only want to print the name in the function but we pass a complete person object to the function. Of course this is no issue but it forces us to call `personObj.name` inside of our function. We can condense this code with destructuring:
```
const printName = ({name}) => {
    console.log(name);
}
printName({name: 'Riddhi Lalakiya', age: 27}); // prints 'Riddhi Lalakiya'
```

We get the same result as above but we save some code. By destructuring, we simply pull out the `name` property and store it in a variable/ argument named `name` which we then can use in the function body.

### Coding Exercise 2: Array Methods

Your task is to add the missing logic to a `transformToObjects()` function that should transform a list of numbers into a list of JavaScript objects.

In the newly returned array, every object must have a `val` key and the input array's number as a value.

For example, for the provided input `[1, 2, 3]` the `transformToObjects([1, 2, 3])` function should return `[{val: 1}, {val: 2}, {val: 3}]`.

#### Example Code:
```
function transformToObjects(numberArray) {
    // Todo: Add your logic
    // should return an array of objects
}
```

#### Exercise Practice:
```
function transformToObjects(numberArray) {
    // Todo: Add your logic
    // should return an array of objects
    const editedNumberArray = numberArray.map(
        (number) => ({val: number})
    )
    return editedNumberArray;
}

```

You also find [section slides](./slides/slides.pdf).