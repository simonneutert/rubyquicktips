---
layout: post
title: Using Hash as Recursive Function with Memoization
date: '2012-03-22T06:00:06+01:00'
tags:
- ruby
- submission
tumblr_url: http://rubyquicktips.com/post/19720734665/using-hash-as-recursive-function-with-memoization
---
We can define a new Hash in a smart way by using Hash#new and passing it a block:


  h    = Hash.new {|hash,key| hash[key] = hash[key-1] + hash[key-2]}
h[1] = 0
h[2] = 1

puts h[3] #=> 1
puts h[100] #=> 218922995834555169026


Here an example of famous Collatz Conjecture:


  h    = Hash.new {|hash,n| hash[n] = 1 + (n.odd? ? hash[3*n+1] : hash[n/2])}
h[1] = 1

puts h[100] #=> 26
puts h[1000] #=> 112


via: thoughbot’s blog
