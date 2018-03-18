---
layout: post
title: Inject your enumerables
date: '2010-01-17T12:11:00+01:00'
tags:
- ruby
- intermediate
- advanced
tumblr_url: http://rubyquicktips.com/post/338980244/inject-your-enumerables
---
Every class that inherits from Enumerable - such as Array or Hash f.e. - inherits a method called inject.

inject combines the elements of the object it is called on (an Array or Hash f.e.) by applying the given block to an accumulator value and each element in turn.
Here are some examples:


  # Sum some numbers
(5..10).inject {|sum, n| sum + n } #=> 45
# Multiply some numbers
(5..10).inject(1) {|product, n| product * n } #=> 151200

# find the longest word
longest = %w{ cat sheep bear }.inject do |memo,word|
  memo.length > word.length ? memo : word
end
longest #=> "sheep"

# find the length of the longest word
longest = %w{ cat sheep bear }.inject(0) do |memo,word|
  memo >= word.length ? memo : word.length
end
longest #=> 5


Examples taken from the Ruby API.
