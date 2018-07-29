---
layout: post
title:      "What is NodeJS? (Part 2)"
date:       2018-07-29 22:15:49 +0000
permalink:  what_is_nodejs_part_2
---

To continue the previous post about Node, let's first download it. The link and directions can be found [here](http://nodejs.org/en/download/).

Once Node has been installed, we can pull up the terminal and acess the node command. What the node command does is pull up the interactive shell, Node REPL( read-eval-print-loop). In this shell, we can run regular JS commands like creating and executing functions. 

```
$ node
> console.log("HELLO!")
HELLO!
undefined
> 1+1
2
> greet = (name) => {
... console.log("WELCOME " + name)
... }
[Function: greet]
> greet("Haley")
WELCOME Haley
undefined
> 
```

While the sandbox is fun, Node has a useful ability to create a server using a built-in HTTP module, which allows Node to transfer data over the Hyper Text Transfer Protocol (HTTP).

To include the HTTP module, we use the require() method:

`const http = require('http');`

The HTTP module can then create an HTTP server that listens to server ports and gives a response back to the client. Let's say the following code below is saved in a file named beginner.js. 

```
const http = require('http');
const port = 3000

// create a server using the createServer() function that takes a function with 2 arguments, the request from the client and the response to the client

http.createServer(function (req, res) {
  res.writeHead(200, {'Content-Type': 'text/html'}); // create HTTP header displayed as HTML
  res.write('Hello World!'); //write a response to the client
  res.end(); //end the response
}).listen(port); //the server object listens on port
```

Now, if you run the file with node, and open up localhost:3000, you should see the text "Hello World". While node provides the foundation for building your own server, because the http module is low-level and creating web applications using it would be very time consuming, we have many frameworks available to help. 

Some popular frameworks used with Node are: 
* Express - the most popular frameworks to use with Node currently. It is one of the four components of the MEAN (MongoDB, Express, AngularJS, NodeJS)  stack which I've come across frequently when reading about web applications where it is used as middleware and as a routing framework. Express is known for being minimalistic so it is easy to build and scale for production. 
* Sails - a realtime MVC framework based on Express and Socket.io. It is most famous for building data-driven APIs and uses [Waterline](http://waterlinejs.org/) for object related mapping and db solutions. It is inspired by the Ruby on Rails framework that follows convention over configuration. 
* Hapi - was created and maintained by Walmart. It is considered to be the perfect choice for enterprise-size applications because it enables collaboration through a plugin system that allow users to work on separate components without affecting the rest of the application. 
* Meteor -  is a full stack framework for building websites and applications for any device (mobile iOS and Android as well). I've also read that Meteor is great for real time applications because it uses hot code pushing, which is a feature that allows all clients connected to the service to get automatic code pushes, making updating quick and easy.

There are a bunch of other frameworks out there but these four are the only ones I've read up documentation on (mainly on my journey to build my own real-time chat application). For more, check the link [here](http://nodeframework.com/) for a more extensive list. 

