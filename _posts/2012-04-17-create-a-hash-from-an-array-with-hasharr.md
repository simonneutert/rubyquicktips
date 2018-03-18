---
layout: post
title: Create a hash from an array with Hash[*arr]
date: '2012-04-17T08:01:36+02:00'
tags:
- ruby
- submission
tumblr_url: http://rubyquicktips.com/post/21257842435/create-a-hash-from-an-array-with-hasharr
---
The Hash::[] class method can be used in addition to the splat operator to create a hash from an array.


  arr = [:a, 1, :b, 2]
Hash[*arr]
# => {:a => 1, :b => 2}
