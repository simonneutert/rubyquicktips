---
layout: post
title: How to initialize a multidimensional Array
date: '2010-07-22T13:00:00+02:00'
tags:
- ruby
- beginner
tumblr_url: http://rubyquicktips.com/post/844746058/how-to-initialize-a-multidimensional-array
---
Array.new takes a block you can use to initialize a multidimensional Array:

a = Array.new(8) { Array.new(8) }


This example will create a two-dimensional Array with a size of 8 × 8 elements.

(via Nooby question : multidimensional arrays)
