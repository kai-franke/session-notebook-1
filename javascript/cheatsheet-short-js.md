- [JavaScript Basics](#JavaScript-Basics)

  - [Selecting HTML Elements: `.querySelector()`](#Selecting-HTML-Elements-querySelector)
  - [Add Interaction: `.addEventListener()`](#Add-Interaction-addEventListener)
  - [Add/remove & toggle classes: `.classList.`](#Add-remove-toggle-classes-classList)
  - [Resources – JavaScript Basics](#Resources-JavaScript-Basics)
  - [Challenges](#Challenges-JS-Basics)

- [JS Variables and Numbers](#JS-Variables-and-Numbers)

  - [Variable Declarations](#Variable-Declarations)
  - [Primitive Data Types](#Primitive-Data-Types)
  - [Math & Operators](#Math_and_Operators)
  - [Assignment Operators](#Assignment-Operators)
  - [Resources – JS Variables and Numbers](#Recources-JS-Variables-and-Numbers)
  - [Challenges](#Challenges-JS-Variables-and-Numbers)

- [JS Conditions and Booleans](#JS-Conditions-and-Booleans)

  - [Control Flow: `if` / `else`](#Control-Flow-if-else)
  - [Ternary Operator: `?` `:`](#Ternary-Operator)
  - [Advanced: The strangeness of boolean coercion and making use of non-strict equality](#Advanced)
  - [Resources – JS Conditions and Booleans](#Resources-JS-Conditions-and-Booleans)
  - [Challenges](#Challenges-JS-Conditions-and-Booleans)

- [JS Functions](#JS-Functions)

  - [Functions](#Functions)
  - [Function Declarations](#Function-Declarations)
  - [Parameters](#Parameters)
  - [Function Calls](#Function-Calls)
  - [Scope](#Scope)
  - [Function scope](#Function-scope)
  - [Global scope](#Global-scope)
  - [Resources](#Resources-Functions)
  - [JS Functions](#Challenges-JS-Functions)

- [JS Functions 2](#JS-Functions-2)
  - [Return Statements](#Return-Statements)
  - [Early Return Statements](#Early-Return-Statements)
  - [Arrow Function Expressions](#Arrow-Function-Expressions)
  - [Resources](#Resources-JS-Functions-2)
  - [Challenges](#Challenges-JS-Functions-2)

---

# JavaScript Basics

<a name="JavaScript-Basics"></a>

## Learning Objectives

- Connect a JavaScript file with `<script src="./index.js" defer></script>`
- Log to the console
- Select elements with `querySelector`
- Add, remove and toggle CSS classes on `click` with `addEventListener`

---

<a name="Selecting-HTML-Elements-querySelector"></a>

## Selecting HTML Elements: `.querySelector()`

<details>
Before we can add interactivity, we need to select the necessary HTML-Elements:

```html
<body>
  <main class="main" id="main" data-js="main">...</main>
</body>
```

```js
const mainElement = document.querySelector('[data-js="main"]');
```

```js
// tag as identifier
const mainElement = document.querySelector("main");
// class as identifier -> .
const mainElement = document.querySelector(".main");
// id as identifier -> #
const mainElement = document.querySelector("#main");
```

</details>

<a name="Add-Interaction-addEventListener"></a>

## Add Interaction: `.addEventListener()`

<details>
The method `addEventListener` is used to react to events.

```html
<button type="button" data-js="button">Log into console</button>
```

First you specify the kind of event, e.g. **click**, then you define what code should be executed
when the event is triggered. You write that code between the `{}` brackets, e.g. a `console.log`.

```js
const button = document.querySelector('[data-js="button"]');
button.addEventListener("click", () => {
  console.log("Yeah");
});
```

There different events you can listen to, for example:

```js
button.addEventListener("mouseover", () => {});
```

```js
button.addEventListener("keydown", () => {});
```

> [list of event types](https://developer.mozilla.org/en-US/docs/Web/Events#event_listing).

</details>

<a name="Add-remove-toggle-classes-classList"></a>

## Add/remove & toggle classes: `.classList.`

<details>
You can add, remove and toggle classes, e.g. to change the styling of an element.

```html
<main data-js="main">
  <button type="button" data-js="button">Add a class</button>
</main>
```

Add **page--primary** class to the above main section by using the `selectedElement.classList.add`
method:

```js
const main = document.querySelector('[data-js="main"]');
const button = document.querySelector('[data-js="button"]');
button.addEventListener("click", () => {
  main.classList.add("page--primary");
});
```

A click on the button adds the class **page--primary** to the main element:

```html
<main data-js="main" class="page--primary">
  <button type="button" data-js="button">Add a class</button>
</main>
```

You can also remove or toggle a class in the same way:

```js
main.classList.remove("page--primary");
```

```js
main.classList.toggle("page--primary");
```

</details>
<a name="Resources-JavaScript-Basics"></a>

## Resources

<details>
### Connect a JavaScript file

[The Script element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script)

### Hello World

[Console](https://developer.mozilla.org/en-US/docs/Web/API/Console)

### Selecting HTML Elements

[Document](https://developer.mozilla.org/en-US/docs/Web/API/Document)

[Using data attributes](https://developer.mozilla.org/en-US/docs/Learn/HTML/Howto/Use_data_attributes)

[document.querySelector](https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelector)

[data-\* attribute](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/data-*)

### Add Interaction

[.addEventListener()](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener)

[Event reference](https://developer.mozilla.org/en-US/docs/Web/Events#event_listing)

### Add/remove & toggle classes

[classList](https://developer.mozilla.org/de/docs/Web/API/Element/classList)

</details>

<a name="Challenges-JS-Basics"></a>

## Challenges

<details>

- [Console Methods `console.log()` a](https://codesandbox.io/s/js-console-01-a-yriwbj)

- [Console Methods `console.log()` b](https://codesandbox.io/s/js-console-01-b-o275lh)

- [Fix the errors in a Survey App a](https://codesandbox.io/s/js-errors-01-a-rhntrf)

- [Fix the errors in a Survey App b](https://codesandbox.io/s/js-errors-01-b-1teglv)

- [Dark Mode a](https://codesandbox.io/s/js-darkmode-01-a-fx6928)

- [Dark Mode b](https://codesandbox.io/s/js-darkmode-01-b-9iniru)

</details>

---

---

[🌑👣🌕 Top 🌕👣🌑](#Top)

<a name="JS-Variables-and-Numbers"></a>

# JS Variables and Numbers

## Learning Objectives

- knowing the difference between `var`, `let` and `const`
- understanding the different data types
- using basic math operations

---

<a name="Variable-Declarations"></a>

## Variable Declarations

<details>

```js
const aNewVariable = 1234;
```

The keyword `let` is only used when you need to reassign a value, for example when you want to
increase a counter.

```js
let counter = 0;
counter = counter + 1; // reassigning the value of counter
```

</details>

<a name="Recources-JS-Variables-and-Numbers"></a>

## Resources

<details>
- [Operator Precedence MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Operator_Precedence)

## </details>

<a name="Challenges-JS-Variables-and-Numbers"></a>

## Challenges

<details>

- [Data for a social media post a](https://codesandbox.io/s/js-variables-numbers-sm-post-01a-9skjpx)
- [Data for a social media post b](https://codesandbox.io/s/js-variables-numbers-sm-post-01b-0ed6mi)
- [Simple calculator a](https://codesandbox.io/s/js-operators-calculator-01a-x2y180)
- [Simple calculator b](https://codesandbox.io/s/js-operators-calculator-01b-dzku84)
- [Counter a](https://codesandbox.io/s/js-counter-01a-p7q2o4)
- [Counter b](https://codesandbox.io/s/js-counter-01b-h9nr4b)
- [Counter b2](https://codesandbox.io/s/js-counter-01b2-6e64wt)
- [Calculator a](https://codesandbox.io/s/js-calculator-01a-cuzd43)
- [Calculator a]()

</details>

---

---

[🌑👣🌕 Top 🌕👣🌑](#Top)

<a name="JS-Conditions-and-Booleans"></a>

# JS Conditions and Booleans

## Learning Objectives

- using conditions to control the program flow
- understanding what booleans and truthy/falsy values are
- working with comparison and logical operators
- writing ternary expressions

---

<a name="Control-Flow-if-else"></a>

## Control Flow: `if / else`

<details>
With an if statement we can control whether a part of our code is executed or not, based on a
condition.

```js
const isSunShining = true;
if (isSunShining) {
  // code that is executed only if condition "isSunShining" is true
}
```

The else block is executed only if the condition is `false`.

```js
const isSunShining = false;
if (isSunShining) {
  // code that is executed only if condition "isSunShining" is true
} else {
  // code that is executed only if condition "isSunShining" is false
}
```

The condition expression between the `()` brackets can be composed of logical or comparison
operators as well. You can distinguish between more cases by chaining `else if` statements:

```js
if (hour < 12) {
  console.log("Good Morning.");
} else if (hour < 18) {
  console.log("Good afternoon.");
} else if (hour === 24) {
  console.log("Good night.");
} else {
  console.log("Good evening.");
}
```

If the condition is not a boolean, it is converted into one by type coercion. This can be used to
check whether a value is not 0 or an empty string:

```js
const name = "Alex";
if (name) {
  console.log("Hi " + name + "!"); // only executed if name is not an empty string
}
```

</details>

<a name="Ternary-Operator"></a>

## Ternary Operator: `? :`

<details>
With if / else statements whole blocks of code can be controlled. The ternary operator can be used
if you want to decide between two _expressions_, e.g. which value should be stored in a variable:

```js
const greetingText = time < 12 ? "Good morning." : "Good afternoon.";
```

The ternary operator has the following structure:

```js
condition ? expressionIfTrue : expressionIfFalse;
```

If the condition is true, the first expression is evaluated, otherwise the second expression. The
ternary operator can be used to decide which function should be called:

```js
isUserLoggedIn ? logoutUser() : loginUser();
```

It can also distinguish which value should be passed as an argument to a function:

```js
moveElement(xPos > 300 ? 300 : xPos); // the element can't be moved further than 300.
```

> ❗️ The operator can only distinguish between two _expressions_ like values, math / logical
> operations or function calls, not between _statements_ like variable declarations, if / else
> statements or multi-line code blocks.

</details>

<a name="Advanced"></a>

## Advanced: The strangeness of boolean coercion and making use of non-strict equality

<details>
<summary>🫣 This is an advanced topic and not important for the challenges. Click to expand if you're curious.</summary>

Assume you want to check if a variable has a useful value for us to work with. `if(variable)` does
in fact not check if `variable` is defined but rather if it is truthy. Take a look at these
examples:

- `if(undefined)` → falsy, won't execute
- `if(null)` → falsy, won't execute
- `if("")` → falsy, won't execute, but might still be a useful variable  
  (e.g. when user clears an input field)
- `if(0)` → falsy, won't execute, but might still be a useful variable  
  (e.g. when user wants to set the volume to `0`)
- `if(" ")` → truthy, will execute
- `if(-1)` → truthy, will execute

It's useful to define a variable as not having a value when it's `undefined` or `null`. We can check
for that like this:

```js
if (variable != null) {
  console.log('This will be logged even if variable is 0 or ""');
}
```

This is one of the rare valid use cases for non-strict comparison (`!=` instead of `!==`).

JavaScript tries to coerce the compared values into the same type. And just like `"3" == 3` is
`true`, `undefined == null` is also `true`. This also works with `!=` instead of `==`.

> ⚠️ Remember that this is an exception for using non-strict equality. **Strict equality should
> otherwise always be preferred.**

</details>

<a name="Resources-JS-Conditions-and-Booleans"></a>

## Resources

<details>

### Operators

[MDN Comparison Operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators#comparison_operators)

[MDN Logical Operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators#logical_operators)

### if / else statements

[MDN about if else](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/if...else)

### Ternary Operator

[MDN Ternary Operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Conditional_Operator)

</details>

<a name="Challenges-JS-Conditions-and-Booleans"></a>

## Challenges

<details>

- [Truthy and Falsy values a](https://codesandbox.io/s/truthy-and-falsy-01a-rui6pk)
- [Truthy and Falsy values b](https://codesandbox.io/s/truthy-and-falsy-01b-b62tpj)
- [Converting boolean values to strings a](https://www.codewars.com/kata/53369039d7ab3ac506000467/train/javascript)
- [Converting boolean values to strings b](https://www.codewars.com/kata/53369039d7ab3ac506000467/solutions/javascript)
- [Grasshopper - If/else syntax debug a](https://www.codewars.com/kata/53369039d7ab3ac506000467/train/javascript)
- [Grasshopper - If/else syntax debug b](https://www.codewars.com/kata/57089707fe2d01529f00024a/solutions/javascript)
- [Grasshopper - Personalized Message a](https://www.codewars.com/kata/5772da22b89313a4d50012f7/train/javascript)
- [Grasshopper - Personalized Message b](https://www.codewars.com/kata/5772da22b89313a4d50012f7/solutions/javascript)
- [Drink about a](https://www.codewars.com/kata/56170e844da7c6f647000063/train/javascript)
- [Drink about b](https://www.codewars.com/kata/56170e844da7c6f647000063/solutions/javascript)
- [Teenager check a](https://codesandbox.io/s/js-teenager-check-01a-nsnre7)
- [Teenager check b](https://codesandbox.io/s/js-teenager-check-01b-wop7vo)

</details>

---

---

[🌑👣🌕 Top 🌕👣🌑](#Top)

<a name="JS-Functions"></a>

# JS Functions

## Learning Objectives

- writing functions in JavaScript
- calling functions
- using function parameters
- learning what 'scope' is

---

<a name="Function-Declarations"></a>

## Function Declarations

<details>

The **function declaration** consists of:

- the function keyword
- the function name
- the function body (Javascript statements / Javascript code)

```js
function greet() {
  console.log("Hi Friends!");
  console.log("Nice to be here.");
}
```

</details>

<a name="Parameters"></a>

### Parameters

<details>
Parameters can be used like predefined variables inside the
function body. When declaring a function we are free to choose a name for the parameters , but
descriptive, short names should be chosen.

```js
function printLetter(name) {
  console.log("Hi " + name + ", hope you are fine. Love, Johnny");
}
function printSum(first, second, third) {
  const sum = first + second + third;
  console.log("The sum of your numbers is: " + sum);
}
```

</details>

<a name="Function-Calls"></a>

## Function Calls

<details>
When functions are defined you can call them by writing their name, followed by parentheses
("rounded brackets"). If the functions consume parameters you can pass them as arguments in the
brackets.

```js
greet();
/*
This will cause the following to be logged into the console:
Hi Friends!
Nice to be here.
*/
printLetter("Max");
printLetter("Jordan");
/*
This will cause the following to be logged into the console:
Hi Max, hope you are fine. Love, Johnny
Hi Jordan, hope you are fine. Love, Johnny
*/
printSum(1, 2, 3);
printSum(3, 4, 5);
/*
This will cause the following to be logged into the console:
The sum of your numbers is: 6
The sum of your numbers is: 12
*/
```

</details>

<a name="Resources-Functions"></a>

## Resources

<details>
[MDN docs: Functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions)
[MDN docs: Scope](https://developer.mozilla.org/en-US/docs/Glossary/Scope)
</details>

<a name="Challenges-JS-Functions"></a>

## Challenges

<details>

- [Basic functions a](https://codesandbox.io/s/js-basic-functions-01a-d6j9pr)
- [Basic functions b](https://codesandbox.io/s/js-basic-functions-01b-7tydx3)
- [Functions with parameters 01 a](https://codesandbox.io/s/js-functions-with-parameters-01a-nt8m1q)
- [Functions with parameters 01 b](https://codesandbox.io/s/js-functions-with-parameters-01b-9lu4n4)
- [Functions with parameters 02 a](https://codesandbox.io/s/js-functions-with-parameters-02a-4q1qwz)
- [Functions with parameters 02 b](https://codesandbox.io/s/js-functions-with-parameters-02b-ru361m)
- [Functions and DOM manipulation a](https://codesandbox.io/s/functions-and-dom-manipulation-01a-jm46ly)
- [Functions and DOM manipulation b](https://codesandbox.io/s/functions-and-dom-manipulation-01b-skdtys)
- [Functions and DOM manipulation b2](https://codesandbox.io/s/functions-and-dom-manipulation-01b2-r2jr07)

## </details>

---

---

[🌑👣🌕 Top 🌕👣🌑](#Top)

<a name="JS-Functions-2"></a>

# JS Functions 2

## Learning Objectives

- What a return statement of a function is and how to use it in your JavaScript functions
- What an `early return` is
- How to write functions with the `fat arrow notation`

---

<a name="Return-Statements"></a>

## Return Statements

<details>
A function can return a value back to the place where it was called. 
This is done via a `return statement`.

```js
function add3Numbers(first, second, third) {
  const sum = first + second + third;
  return sum;
}
```

The `return statement` begins with the keyword `return` followed by an expression. In this case,
the expression is the variable sum. Its value is returned by the function and can be stored when the
function is called:

```js
const firstSum = add3Numbers(1, 2, 3);
// the return value is stored in "firstSum", namely 6
const secondSum = add3Numbers(4, 123, 33);
// the return value is now stored in "secondSum", namely 160
```

> 💡 An expression is anything that produces a value: a variable, a hardcoded value like `true` or
> `6`, a math operation like `2 + 3` or even another function call!
> [This article](https://www.joshwcomeau.com/javascript/statements-vs-expressions/) explains this in
> greater depth.
> By this, we can outsource computations and / or decision processes and continue using the returned
> value in the program.

A function can return only one expression value, but can have multiple return statements, in
combination with if else statements for example:

```js
function checkInputLength(inputString) {
  if (inputString.length > 3) {
    return true;
  } else {
    return false;
  }
}
```

</details>

<a name="Early-Return-Statements"></a>

## Early Return Statements

<details>
As soon as a return statement is reached in a function call, the function execution is ended. The
following `console.log()` is therefore never reached:

```js
function testFunction() {
  return "a returned string";
  console.log("I am never logged in the console.");
}
```

This behavior can be used to our advantage as early return statements. Sometimes we want to execute
certain parts of our code only if a condition applies. We can check this with an if else statement.
When multiple conditions are in place, the code becomes harder to read and to understand:

```js
function setBackgroundColor(color) {
  if (typeof color === "String") {
    if (color.startsWith("#")) {
      if (color.length >= 7) {
        body.style.backgroundColor = color;
      }
    }
  }
}
```

An alternative approach is to terminate the function with early return statements:

```js
function setBackgroundColor(color) {
	// first condition
	if(typeOf color !== 'String') {
		return;
	}
	// second condition
	if(!color.startsWith('#')) {
		return;
	}
	// third condition
	if(color.length < 7) {
		return;
	}
	// only if all 3 conditions are passed the final line of code is executed.
	body.style.backgroundColor = color;
}
```

This way of writing the code is more readable

💡 Hint: A return statement can be left empty, the returned value is then `undefined`.

</details>

<a name="Arrow-Function-Expressions"></a>

## Arrow Function Expressions

<details>
Next to the classic function declaration, JavaScript has a second way to write functions as
`arrow function expressions`:

```js
const addNumbers = (first, second) => {
  return first + second;
};
```

The function is saved like a variable with the keyword `const`. The parameters are written normally
in round brackets followed by an fat arrow `=>`. Then the function body is written in curly
brackets.

### Implicit Return Statements

The advantage of arrow functions are possible shorter notations when certain criteria apply:

1. Omit the round brackets around the parameters: This is possible, if there is only one input:
   ```js
   const addOne = (number) => {
     return number + 1;
   };
   ```
2. Implicit return statements: If the function consists only of a return statement, the curly
   brackets and the return keyword can be omitted:
   ```js
   const addNumbers = (first, second) => {
     return first + second;
   };
   ```
   can be rewritten as:
   ```js
   const addNumbers = (first, second) => first + second;
   ```

> 💡 This shorthand notation comes in handy as soon as we work with callback functions in a few
> days. So try to remember this feature.
> 💡 Maybe you remember the syntax of the `addEventListener` method. We encountered these arrow
> functions there already!
>
> ```js
> button.addEventListener('click',() => {
> 	...
> })
> ```

</details>

<a name="Resources-JS-Functions-2"></a>

## Resources

<details>

- [Statements vs Expressions by Josh Comeau](https://www.joshwcomeau.com/javascript/statements-vs-expressions/)

</details>

<a name="Challenges-JS-Functions-2"></a>

## Challenges

<details>

- [Calculations a](https://codesandbox.io/s/js-functions-2-calculations-01a-43zhms)
- [Calculations b](https://codesandbox.io/s/js-functions-2-calculations-01b-3krtc4)
- [Greeting Page a](https://codesandbox.io/s/js-functions-2-greeting-page-01a-fhkpm9)
- [Greeting Page b](https://codesandbox.io/s/js-functions-2-greeting-page-01b-ryxy58)
- [Progress Bar a](https://codesandbox.io/s/js-functions-2-progress-bar-01a-ctkeo2)
- [Progress Bar b](https://codesandbox.io/s/js-functions-2-progress-bar-01b-ceg30l)
- [Convert Arrow Functions a](https://codesandbox.io/s/js-functions-2-convert-arrow-functions-01a-n0ydj9)
- [Convert Arrow Functions b](https://codesandbox.io/s/js-functions-2-convert-arrow-functions-01b-qlrnyo)
</details>
