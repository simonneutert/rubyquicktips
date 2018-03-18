---
layout: post
title: How to define infinite numbers
date: '2011-02-21T08:00:00+01:00'
tags:
- ruby
- submission
tumblr_url: http://rubyquicktips.com/post/3420059472/how-to-define-infinite-numbers
---
You can define the “number” ‘infinity’ (or ’-infinity’) in Ruby like this:


  1.0/0
=> Infinity

-1.0/0
=> -Infinity


Infinity and -Infinity behave just like you expect them to: they are always bigger - or always smaller, respectively - than any number you compare it to.
The Xing Devblog had a great post recently about using Ruby’s infinity in Rails, with some thoughts on when you might want to use it (or not).

P.S.: the Float class in Ruby 1.9.2 provides an Infinity constant you can use:


  Float::INFINITY
=> Infinity


This tip was submitted by makoto.
