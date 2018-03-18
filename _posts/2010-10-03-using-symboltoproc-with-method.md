---
layout: post
title: 'Using Symbol#to_proc with #method'
date: '2010-10-03T06:59:23+02:00'
tags:
- ruby
- intermediate
- submission
tumblr_url: http://rubyquicktips.com/post/1233141824/using-symboltoproc-with-method
---
Following up on the Quicktip on Symbol#to_proc, one of my favorite idioms is using this shortcut with a call to #method:

ruby-1.8.7 > def foo(x) ; puts x ; end
=> nil

ruby-1.8.7 > (1..5).each(&method(:foo))
1
2
3
4
5
=> 1..5


Have a look at the documentation on Object#method.

This tip was submitted by Dean Strelau.
