---
layout: post
title:      "Rails Project - My Bookshelf"
date:       2018-03-05 16:46:01 +0000
permalink:  rails_project_-_my_bookshelf
---


For my Rails final project, I created a book cataloging website that allows users to view and search new books released and creating reading lists to organize and track their reading progress. Before starting every project, I like to physically write out and brainstorm how I want the application to work. First, I noted the models that I would need to make this work: Users, Books, Genres, Authors, Reading Lists, ListBooks(to map the many-to-many association between lists and books). For my Users class, I used the Devise gem to handle loggining in and signing up. I also added Omniauth to my application as a way for Github users to login. 

For my models, I added a few validations. For example, with books, it would make no sense for an author to have two of the same books so I added the validation:

```
class Book < ApplicationRecord

validates :title, uniqueness: {scope: :author_id}

```

Also, I created an ActiveRecord SQL query that would pull the most popular novel based on how many reading lists it was currenty added onto. I thought this would be a good function for user experience. 

After I had all of my migrations and models built out, I tackled the controller and views. I started creating an index and show page for books, authors, reading lists and genres. Once that was completed, I took on the new and create controller actions and views. I used partials for those and making my code DRY. 

One of the main challenges I ran into was with nesting. I had to go back to my lessons and google search them to refresh my memory on how they worked. Nested attributes allow you to save attributes on associated records through the parent and I created nested attributes for admins to create new authors and associate new books to them at the same time. See below:

```
class Author < ActiveRecord::Base
   has_many :books

 accepts_nested_attributes_for :books
```

I also created nested resources for users and their reading lists since reading lists are logically children of the users. 
```
resources :users do
  resources :reading_lists
end
```

This project was definitely a huge learning experience. Starting a project from scratch and debugging it every step of the way is a lot of work and gives a better perspective on how programming works. Lab lessons, while extremely useful in teaching new concepts, don't give the full perspective on how to connect all the concepts together.

That being said, I think my web application could still use more work. Some features I would like to add later on to the project are:

* **Reviews**: Each user should be able to leave a review for the book they are reading. This would generate a greater social aspect on the website.
*** Ratings System**: Similar to reviews, I believe rating the books will give a greater feel for community bonding and provide more value for users on the website to decide whether or not to pick up the new book; as not all users will want to leave a lenghty review.
* **Admin roles**: Currently, I have a very basic admin functionality but if more features were to be added, I would like to expand the role to include moderators. They would have less authority and rights compared to Admins but would still be able to run certains aspects of the website.  
