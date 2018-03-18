---
layout: post
title: Using Enumerable::inject to modify a hash
date: '2012-01-26T06:00:05+01:00'
tags:
- ruby
- submission
tumblr_url: http://rubyquicktips.com/post/16508417798/using-enumerableinject-to-modify-a-hash
---
Ever wanted to modify the keys and values of a Hash? Enumerable::inject has you covered.

Try this snippet from Stack Overflow:


  my_hash = { a: ''foo'', b: ''bar'' }
# => {:a=>"foo", :b=>"bar"}
a_new_hash = my_hash.inject({}) { |h, (k, v)| h[k.upcase] = v.upcase; h }
# => {:A=>"FOO", :B=>"BAR"}
