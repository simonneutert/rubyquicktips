---
layout: post
title: Enumerable#each_with_object
date: '2012-03-29T07:00:06+02:00'
tags:
- ruby
- rubyonrails
tumblr_url: http://rubyquicktips.com/post/20104758978/enumerableeachwithobject
---
Enumerable#each_with_object is quite similar to Enumerable#inject, yet slightly different. From the Ruby 1.9 and Rails 3 API docs:


  Iterates the given block for each element with an arbitrary object given, and returns the initially given object.
  
  Iterates over a collection, passing the current element and the memo to the block. Handy for building up hashes or reducing collections down to one object.



  evens = (1..10).each_with_object([]) {|i, a| a << i*2 }
#=> [2, 4, 6, 8, 10, 12, 14, 16, 18, 20]

%w(foo bar).each_with_object({}) { |str, hsh| hsh[str] = str.upcase }
# => {''foo'' => ''FOO'', ''bar'' => ''BAR''}


As BiHi noted on this tip on Enumerable#inject, its example can be slightly simplified using each_with_object instead of inject:


  my_hash = { a: ''foo'', b: ''bar'' }
# => {:a=>"foo", :b=>"bar"}

my_hash.each_with_object({}) { |(k,v), h| h[k.upcase] = v.upcase }
# => {:A=>"FOO", :B=>"BAR"}
