---
layout: post
title: 'Rails'' index_by: the easy way to convert an Array to a Hash'
date: '2012-04-12T13:28:37+02:00'
tags:
- rubyonrails
tumblr_url: http://rubyquicktips.com/post/20959548298/rails-indexby-the-easy-way-to-convert-an-array
---
As Aditya Sanghi notes in “Quickly convert an Array to a Hash”, a very quick way to convert an Array to a Hash, is to use Rails’ Enumerable#index_by:


  Post.all.index_by { |post| post.id }
# => { 1 => #<Post ...>, 2 => #<Post ...>, ... }

Post.all.index_by(&:title)
# => { "My first post" => #<Post ...>, "My second post" => #<Post ...>, ... }
