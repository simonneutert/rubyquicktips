---
layout: post
title: Convert Object to Array
date: '2011-08-31T08:00:05+02:00'
tags:
- ruby
tumblr_url: http://rubyquicktips.com/post/9618833891/convert-object-to-array
---
Have you ever been in a situation where you needed a method that does all of the following?

Convert nil to an empty Array, and
convert a non-Array variable n to [n], and
leave the Array variable as is.
The way to achieve this, is using the little known method Array():


  Array(nil) # => []
Array([])  # => []
Array(1)   # => [1]
Array([2]) # => [2]
