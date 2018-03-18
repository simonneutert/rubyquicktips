---
layout: post
title: Shortcut for calling a method on each collection item
date: '2010-02-28T18:00:00+01:00'
tags:
- ruby
- beginner
- intermediate
- submission
tumblr_url: http://rubyquicktips.com/post/417820906/shortcut-for-calling-a-method-on-each-collection
---
There’s a quick way of calling a method for all elements in an array. Instead of doing:

authors = Post.all.map{ |p| p.author }
# or even
authors = Post.all.map do |p|
  p.author
end


…you can just pass &:author to the map method to specify the method that should be called on each element (in this case :author). The ampersand is necessary since map always expects a block.

authors = Post.all.map(&:author)


Reg Braithwaite wrote an excellent introduction to the ampersand operator, blocks and procs in Ruby.map in the Ruby API docs.

This tips was submitted by Simon Baumgartner.
