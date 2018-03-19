---
layout: post
title:      "Form_for vs Form_tag & Partials"
date:       2018-03-19 22:05:48 +0000
permalink:  form_for_vs_form_tag_and_partials
---


 A big section in Rails that I needed extra review on was forms. Since forms are an essential interface for user input in web applications, I thought it'd be helpful to focus a little more on them and the difference between the two form helpers. 
 
 The most basic form helper method is form_tag. It follows the url provided to it and defaults to the POST method unless you specify otherwise. This is used when you want to create a form but don't have a model for it. As a result, we need to specify  A good use for form_tag is for building search functionality. It won't result in any database updates but can help you specify and view results based on a criteria. 
 
 See example below:
```
<%= form_tag("/search", **method: "get"**) do %>
  <%= label_tag(:query, "Search:") %>
  <%= text_field_tag(:query) %>
  <%= submit_tag("Search") %>
<% end %>
```

This will generate the HTML output: 
```

<form accept-charset="UTF-8" action="/search" method="get">
  <input name="utf8" type="hidden" value="&#x2713;" />
  <label for="q">Search for:</label>
  <input id="q" name="q" type="text" />
  <input name="commit" type="submit" value="Search" />
</form>
```

The form_for method is another ActionView helper that offers an additional level of abstraction. This is a good approach if you have an underlying model and are trying to update or add to it, i.e creating a new row in database. For example, if I had a Book model and I wanted to create or edit an instance of it, form_for would be a good idea. 

See below: 
```
<%= form_for @book do |f| %>
  <%= f.label :title %>:<br>
  <%= f.text_field :title %> <br></br>

  <%= f.label :publication_year %>:<br>
  <%= f.text_field :publication_year %> <br></br>
	
	 <%= f.label :author %>:<br>
   <%= f.text_field :author %> <br></br>
	 
	 <%= f.submit%>
<% end %>
	
```

Something you will notice when dealing with forms is that there is a lot of repetition. In the example above, the form for new and edit would be the same. Instead of having the same code and violating the DRY principle, we can use partials. The term partial indicates that they are a part of something, a smaller piece of a template. In order to use partials, we create a file with a name that starts with an underscore to differentiate them from regular views. Then, to reference it in our embedded ruby file(html.erb), we add a call to render. 

```
<h1>Create a New Book</h1>

<%= render partial: "form"%>
```

In conclusion, partials are a great way to break down complex view into more manageable chunks as well as keeping view code DRY.
