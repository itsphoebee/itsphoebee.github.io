---
layout: post
title:      "Hoist Me to the Moon"
date:       2018-06-07 03:28:09 +0000
permalink:  hoist_me_to_the_moon
---


My last blog post was about JS Scope and a great follow up to that topic would be Hoisting. Hoisting is a JavaScript mechanism where variables and function declarations are moved to the top of their scope before code execution. To fully understand what hoisting is, we should first refresh our memory on the way JS is compiled. The JS engine runs in two phases: the compilation phase and the executions phase. During the compilation phase, the engine skips right over the invocation and stores any declarations in memory. Once the compilation phase ends, the execution phase begins and it will ignore the declarations and executes the code line-by-line. 

```
// What we see
console.log(day) //  undefined
var day = “Monday”;
console.log(day) // prints "Monday"
```

In the sample code above, we see the var day declared and expressed as one line but JS will interpret it as:

```
// What JS sees
var day;
console.log(day) // undefined
day = “Monday”;
console.log(day) // prints "Monday"
```
This is because JS will interpret the code and hoist the declaration up top and the assignment is left in place. As a result, variables might actually be available before their declaration (which is why we get undefined instead of an error). Note: this applies to variable and function declarations. Let's see an example with function declarations:

```
superhero1();

function superhero1() {
  var name = `Iron Man`;
  console.log(`${name} is a superhero!`);
}
```

The code above will be interpreted by JS as:
```
//function declaration hoisted
function superhero1() {
  var name = `Iron Man`;
  console.log(`${name} is a superhero!`);
}

//prints "Iron Man is a superhero"
superhero1();
```
All clear, no errors here. Now let's see another example:

```
superhero2();

var superhero2 = function () {
  var name = `Captain America`;
  console.log(`${name} is also a superhero!`);
}
```

Uh oh, this results in a TypeError. This is because function expressions are not hoisted and as a result, functions assigned to variables are not hoisted. Note: Think of functions as first-class VIP members. They will get hoisted before variables. 

Another thing to note is the difference between variables declared with the var keyword and variables declared with let and consts. While variables declared with const and let do get 'hoisted', the JS engine doesn't allow them to be referenced before they've been initialized so instead of undefined we will end up with an error. Let's see an example of both:

```
console.log(hoist); // ReferenceError: hoist is not defined
let hoist = 'The variable has been hoisted.';
console.log(hoistmetoo) // ReferenceError: hoistmetoo is not defined
const hoistmetoo = 'This variable is hoisted too'
```

In conclusion, a good rule of thumb is to (1) declare all of your variables at the top of their scope (2) use let and const instead when applicable.
