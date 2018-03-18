---
layout: post
title: Render collections
date: '2010-04-30T20:00:00+02:00'
tags:
- rubyonrails
- beginner
- intermediate
tumblr_url: http://rubyquicktips.com/post/561339136/render-collections
---
Instead of looping through your collection and rendering a partial for each element like this:

<% @students.each do |student| %>
<%= render :partial => ''person'', :locals => { :person => student } %>
<% end %>


…you can pass the collection directly to the render method:

<%= render :partial => ''person'', :collection => @students %>


Please note that the name of the variable, you can use inside the partial to refer to each element of your collection, has the same name as your partial; and is not derived from the name of your collection. So, in this case use person and not student.

Check the API docs on render.
