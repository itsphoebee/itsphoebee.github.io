---
layout: post
title:      "What is NodeJS? (Part 1)"
date:       2018-07-23 02:55:27 +0000
permalink:  what_is_nodejs_part_1
---


As a recent graduate of Flatiron School, we were taught Ruby on Rails as a backend framework. However, as I transition into job hunting, I've noticed more and more that NodeJS is a very popular choice for backend technology. This led me to start researching more about it to see how it compared to Rails, and here's what I learned: 

What is Node.JS? 
Node.JS is a Javascript runtime environment built in Chrome’s V8 engine. It allows you to execute Javascript code outside of the browser, which it was originally built for, and in a computing environment, such as a server. It is a common misconception but NodeJS is not a framework or a language. **It is a runtime environment**.

What are the advantages of Node?
1. Node is fast. - I hear/read this a lot on blogs and other posts. Node is considered fast because the library behind Node handles non-blocking I/O. What this means it that in your application, the browser and client can send data back and forth each other without waiting on the other to finish. The connection also continues to remain open after the page has loaded so you don't need to refresh or click any buttons to receive new data. 
2. You can use ONE language - Since Node is essentially JS, you can use one language on both the client and server side which should make debugging a lot easier. 
3. It is more flexible. - In comparison with Rails, Rails has extremely strict filenames and structure. I can't count how many times something broke while I was working because of a filename typo. Rails has its own internal logic for looking up files in specific locations while Node apparently does not. All you have to do is require the files by whatever filename you named it. 
4. Great package manager - Node comes with a package manager called npm, and it has a large number of open source tools/libraries and is growing everyday. I believe this is similar to Ruby gems.

Should I learn NodeJS?
This is a little bit more opinionated. I'm choosing to learn it because I want to learn to build real-time applications and because Node is event-based, it is great for handling that. Node is also gaining a lot of publicity because big companies are using it, such as Netflix, LinkedIn, Uber, PayPal, etc. 

More on how to use Node in the next part!





