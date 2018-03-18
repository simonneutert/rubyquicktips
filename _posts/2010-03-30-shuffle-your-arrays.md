---
layout: post
title: Shuffle your Arrays
date: '2010-03-30T11:30:38+02:00'
tags:
- ruby
- beginner
- intermediate
tumblr_url: http://rubyquicktips.com/post/483872482/shuffle-your-arrays
---
From Ruby 1.8.7 on, elements of an Array can be ordered at random using the shuffle method:

a = [ 1, 2, 3 ]           #=> [1, 2, 3]
a.shuffle                 #=> [2, 3, 1]


Check out the API docs on shuffle.
