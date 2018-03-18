---
layout: post
title: Eager loading
date: '2011-06-11T08:41:26+02:00'
tags:
- rubyonrails
tumblr_url: http://rubyquicktips.com/post/6411587940/eager-loading
---
When you load records from the database and also want to access the associated objects for each of these records, it’s a good idea to make use of eager loading. Eager loading reduces the amount of queries made to the database and therefor increases performance.
A good example is an index view where you want to display an overview of information on a particular group of objects, including their associations (for example, if you want to display a list of blogposts and for each of these posts the last - say - three comments).

To make use of eager loading, you can use the :include parameter (Rails 2) or the includes method (Rails 3) respectively when doing your ActiveRecord finds.


  # Rails 2
Blogpost.all(:include => :comments)

# Rails 3
Blogpost.includes(:comments).all


You can also load more than one association and nest the include statements using Arrays and Hashes:


  # Rails 2
Blogpost.all(:include => [:tags, { :comments => :commenter }])

# Rails 3
Blogpost.includes(:tags, { :comments => :commenter }).all


Exactly one database query is performed for each model you want to load.
If you want to know more about eager loading, including why and when to use it, check out the Rails Guide on eager loading.
