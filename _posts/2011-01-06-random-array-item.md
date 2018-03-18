---
layout: post
title: Random Array Item
date: '2011-01-06T20:01:00+01:00'
tags:
- ruby
- submission
tumblr_url: http://rubyquicktips.com/post/2625525454/random-array-item
---
From 1.8.7 on, there is the Array#shuffle method.


  [1,2,3].shuffle # => [2,1,3]


This makes it extremely easy to write Array#random to pick a random item from an array


  class Array
  def random
    shuffle.first
  end
end

[1,2,3,4,5,6,7,8,9].random # => 5
[1,2,3,4,5,6,7,8,9].random # => 1
[1,2,3,4,5,6,7,8,9].random # => 3


This tip was submitted by Justin Baker.
