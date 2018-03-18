---
layout: post
title: Use negative Array indices
date: '2010-08-23T08:00:00+02:00'
tags:
- ruby
- beginner
- submission
tumblr_url: http://rubyquicktips.com/post/996814716/use-negative-array-indices
---
Ruby arrays have some nifty behavior when passed negative array indices. Let’s say you have an array

array = [:a, :b, :c, :d, :e]


You can access the last element in the array by calling

array[-1] # => :e


The second-to-last element has index -2, and so on. Negative indices also work for slicing operations. For example, if you wanted to leave out the last two elements in the array, you would call

array[0..-3] # => [:a, :b, :c]


and if you wanted to remove just the first element of the array,

array[1..-1] # => [:b, :c, :d, :e]


This tip was submitted by Rockwell Schrock.
