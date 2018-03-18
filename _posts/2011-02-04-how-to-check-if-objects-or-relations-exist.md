---
layout: post
title: How to check if objects or relations exist
date: '2011-02-04T02:32:00+01:00'
tags:
- rubyonrails
tumblr_url: http://rubyquicktips.com/post/3096503536/how-to-check-if-objects-or-relations-exist
---
Here’s an interesting fact when checking if objects or relations exist in a collection.
To check if there were any items present in a collection you can do something like this:


  Object.relation.present?


This, however, is better:


  Object.relation.any?


Turns out that - when you request associated objects for the first time - the any? method will perform a COUNT (*) SQL query where as the present? method will perform a SELECT (*) which is infinitely slower than performing a count.


  blog = Blog.first
blog.posts.present?
# SQL (284.1ms)   SELECT * FROM "posts" WHERE ("posts".blog_id = 1)

blog = Blog.first
blog.posts.any?
# SQL (1.2ms)   SELECT count(*) AS count_all FROM "posts" WHERE ("posts".blog_id = 1)


Thanks to Mario and Keith for this tip.
