---
layout: post
title: Quickly convert an Array to a Hash
date: '2012-02-09T06:00:05+01:00'
tags:
- rubyonrails
- ruby
- submission
tumblr_url: http://rubyquicktips.com/post/17306181714/quickly-convert-an-array-to-a-hash
---
As an example, let’s say you want to create an index of ActiveRecord objects by their id. Use the Hash constructor that accepts an Array of key-value pairs and do it in one line:


  posts_by_id = Hash[*Post.all.map{ |p| [p.id, p] }.flatten]


This tip was submitted by http://Fullware.net/.
