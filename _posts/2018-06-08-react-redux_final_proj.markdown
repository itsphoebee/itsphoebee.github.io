---
layout: post
title:      "React-Redux Final Proj"
date:       2018-06-08 20:40:25 +0000
permalink:  react-redux_final_proj
---


My final project in the Flatiron School encompasses the entirety of what I learned these past few months. As usual, it took me about a week to think of a project idea I felt comfortable with. Also, as usual, I stuck to the theme of creating apps parallel to my interests. With the weather in my area finally warming up and the traces of winter and a very temperamental spring edging away, it was also time to switch up my own skincare routines. As a result, SkinCare Rituals was born. 

This single page app I created is dedicated to all the avid skincare fans, as well as casual researchers. Skincare Rituals is here help you sort through the many different routines to combat all skin concerns. I build this app up with a React/Redux front end and a Rails API backend. Here's the [article](https://www.fullstackreact.com/articles/how-to-get-create-react-app-to-work-with-your-rails-api/) that helped me set it up in case anyone is curious and wants to follow along.

The requirements for the project are stated below:

* The code should be written in ES6 as much as possible
* Use the create-react-app generator to start your project.
* Follow the instructions on this repo to setup the generator: create-react-app
* Your app should have one HTML page to render your react-redux application
* There should be 2 container components
* There should be 5 stateless components
* There should be 3 routes
* The Application must make use of react-router and proper RESTful routing
* Use Redux middleware to respond to and modify state change
* Make use of async actions to send data to and receive data from a server
* Your Rails API should handle the data persistence. You should be using fetch() within your actions to GET and POST data from your API — do not use jQuery methods.
* Your client-side application should handle the display of data with minimal data manipulation

I think the hardest part of this assignment was understanding the async action and how it flows. Since I need to get my data from my Rails API, I needed to send a request in order to update my application's state. Using redux middleware with redux-thunk allowed me to define action creators as functions to return functions. The returned function is then executed by Thunk middleware  and dispatches an action with the result of the API call and updates the state accordingly.

I will most definitely continue working on this project as I navigate through my job search and onwards. One of the important things I need to work on more is styling. I need to work on my CSS/HTML skills to make my applications more attractive. 

Check out my code [here](https://github.com/itsphoebee/skin-care-rituals). Please do leave comments and helpful criticism.
