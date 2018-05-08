---
layout: post
title:      "Rails App with a jQuery Front End"
date:       2018-05-08 17:18:19 +0000
permalink:  rails_app_with_a_jquery_front_end
---


For this assignment, I updated my previous Rails app, My Bookshelf, to include dynamic features using jQuery.  Before  I decided to build new functionality, I reviewed my code in its entirety once more to familiarize myself with it. After some time between building this app initially and now, I found that there were some small errors and bugs that I missed the first time around. For example, for my reviews index page, I had intended to show all of a users' reviews but instead I had built it to show all reviews in the database. It was a small fix but a very important one to catch. Once I was in a comfortable spot with what I had built, I reviewed the requirements. 

*** Must render at least one index page (index resource - 'list of things') via jQuery and an Active Model Serialization JSON Backend. **

I created an authors index page and using an AJAX GET request I fetched all of the authors' published novels and using ActiveModel Serialization, I rendered the serialized data in JSON and appended the result to the page. 

*** Must render at least one show page (show resource - 'one specific thing') via jQuery and an Active Model Serialization JSON Backend. **
Also building on the authors views, I updated the authors show page to have a Next and Previous link that allows users to browse through all the authors on the same page using AJAX get request and without refreshing the page. 

*** The rails API must reveal at least one has-many relationship in the JSON that is then rendered to the page. **
On a book's show page, I updated it to render all the reviews a book has. 

*** Must use your Rails API and a form to create a resource and render the response without a page refresh. **
Reviews for books could be created without a page refresh. The review is added to a book and serialized, then submitted via an AJAX POST request. The response becomes the new object in JSON and then appended to the DOM using JavaScript.

*** Must translate the JSON responses into Javascript Model Objects. The Model Objects must have at least one method on the prototype. **
I created a Review prototype object and added a function to it to help format new reviews created.  The object is then appended to the DOM.

Overall, I know there's still a lot of refactoring to be done for my app. I intend to continue building on this after graduation. Some ideas include rendering all of my index pages (books, reading lists, genres) via jQuery and JSON Backend. I may also add in a new Comment class to the Review class so users can respond to each other's reviews. I will also try to implement this feature via jQuery and JSON to limit the number of page refreshes needed. I will try to make the app as close to a single page app as possible. 
