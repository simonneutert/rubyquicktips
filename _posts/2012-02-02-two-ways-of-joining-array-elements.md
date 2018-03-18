---
layout: post
title: Two ways of joining Array elements
date: '2012-02-02T06:00:05+01:00'
tags:
- ruby
- submission
tumblr_url: http://rubyquicktips.com/post/16907529909/two-ways-of-joining-array-elements
---
You can use Array#join to concatenate Array elements to a String:


  [1, 2, 3].join(''+'')
# => "1+2+3"


Array#* has the same effect when you pass it a String:


  [1, 2, 3] * ''+''
# => "1+2+3"


This tip was submitted by Ciur Eugen.
