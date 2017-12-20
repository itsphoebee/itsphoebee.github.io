---
layout: post
title:      "Arrays vs Hashes"
date:       2017-12-20 02:08:41 +0000
permalink:  arrays_vs_hashes
---


I think I'm speaking the truth when I say data storage and retrieval is extremely important in programming. The two forms of data storage we come across in Ruby most frequently are arrays and hashes. I personally had a little trouble understanding the use of hashes, so as a result, I decided to blog about it to summarize what I learned.

We meet arrays pretty early on in our learning journey. Arrays are like lists, a collection of data in some order. You can look up the data in arrays by its index. Similar to a grocery list, for example,  1. milk 2. eggs 3. potatoes. The number corresponds to the index and the item is the data value you are looking for. 

For example: 

grocery_list = ["milk", "eggs", "potatoes"] 
grocery_list[0] = "milk"
grocery_list[1] = "eggs"
grocery_list[2] = "potatoes"

Hashes are different in the sense that it contains pairs of unordered information: a **unique** key and value. The key is unique because it is used to return the value assigned to it. Piggybacking off the grocery list example, this list could probably be from your extremely annoying sibling where 1. milk must be lowfat 2.  eggs are cage free 3. Idaho potatoes. While in arrays you use an index number, in hashes you use the key to locate the data value you are looking for. 

For example: 

grocery_list = {"milk" => "lowfat", "eggs" => "cage-free", "potatoes" => "Idaho"}
grocery_list["milk"] = "lowfat"
grocery_list["eggs"] = "cage-free"
grocery_list["potatoes"] = "Idaho"

So when should you use either one? While arrays are infinitely helpful, they do not allow data to interact. With arrays, its indexes have nothing to do with their values besides the order they come in. But with hashes, you can build them up to use as databases to look up information using nested/multidimensional hashes. I'm a big fan of Harry Potter so let's see the next example:

Hogwarts_students = {
"Harry Potter" => {
       name: "Harry",
       gender: "male",
			 age: 15,
			 house: "Gryffindor",
			 race: "half-blood"
			 },
"Hermione Granger" => {
       name: "Hermione",
			 gender: "female",
			 age: 15,
			 house: "Gryffindor",
			 race: "muggle"
			 },
"Draco Malfoy" => {
       name: "Draco",
			 gender: "male",
			 age: 15,
			 house: "Slytherin",
			 race: "full-blood"
			 }
}

I could continue with the rest of the universe of chraracters but you get the point. Hashes are useful because with them I can associate all of Harry's attributes to him. Arrays can be used to create sequential lists but hashes are your best friend if you need to use different objects and associate them. 


