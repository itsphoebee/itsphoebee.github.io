---
layout: post
title:      "So what's the Scope?"
date:       2018-06-05 22:41:49 +0000
permalink:  so_whats_the_scope
---

One of the most important topics when studying JS is scope. It's also one of the topics I needed extra time working through before understanding. 

So, what is scope? Scope is what determines the visibility of variables and other resources in your code. What this means is that variables have access to other objects within the same scope and those in a broader scope.

What is the point of scope? Why not give everything access to everything? Well, one reason for that is security. For example, it wouldn't make sense or be safe to give everyone the keys to your house.  Only specific users should have access to the stuff they need at a certain time. This is also called the principle of least privilege/authority/exposure in software design. It describes the concept of exposing only what is minimally necessary and hiding everything else. 

In JS, there are two types of scopes: global scope and local scope. If a variable is declared outside a function, it is in the global scope. Variables inside the global scope can be accessed and altered in any other scope. See below for quick example:
```
// global scope
var student = "Simon";
function one() {
  console.log(student); 
}
one()
```

In this example, the student variable is declared in the global scope so function one has access to it and when called, console.log will show "Simon".

 Local scope includes variables that are usable only in a specific part of the code and are defined past the global scope. 

```
  // local scope
function two() {
  var student = "Alice";
  console.log(student); 
	}
	
	function three() {
	console.log(student);
	}

two()
three()
```

In this example, the student variable is declared inside function two and is in the local scope, so only function two will have access to it. When two is called, console.log will show "Alice". However, function three doesn't have access to the variable, and will result in an error stating that student is undefined. 

That was simple enough. Let's go a step further and talk about lexical scope and scope chain. Lexical Scope means that in a nested group of functions, the inner functions have access to the variables and other resources of their parent scope. See below:
```
// Scope A
// name and likes are not accessible
function person() {
    // Scope B
    var name = 'Anna';
    // name is accessible but likes is not accessible
    function hobbies() {
		    // Scope C
		    var likes = "Reading"
        // name and likes are both accessible here
    }
}
```
Notice that lexical scope only works going forward but not backward. This means that children can access parent variables but parents cannot access child variables. 

I really like this picture from the book series "You Don't Know JS". I think it really helps visualizers scope. ![](https://raw.githubusercontent.com/getify/You-Dont-Know-JS/master/scope%20%26%20closures/fig1.png)

The picture above represents a nested scope. Imagine you are looking for your friend and you forgot which floor he lives on. (Let's disregard the idea of phones and directories for now.) The first floor building represents where you are currently and the top level is the global scope. First,  you start on the first floor and search if your friend is there. If not, you go up a level and search there. If you still haven't found him, you just keep going up until the top floor (the global scope) where you either find your friend or you don't and will have to end your search there. 

Here's a [link](https://github.com/getify/You-Dont-Know-JS) to check out "You Don't Know JS". It's completely free and has a lot of information to help beginners learning JS. 


