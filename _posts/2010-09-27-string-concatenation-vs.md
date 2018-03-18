---
layout: post
title: 'String Concatenation: << vs. +='
date: '2010-09-27T12:53:48+02:00'
tags:
- ruby
tumblr_url: http://rubyquicktips.com/post/1197849149/string-concatenation-vs
---
You probably know that both << and += operators are used to append text to the string in ruby. However there is a difference between them. Pay close attention:

original = "foo"
copy = original

The shovel operator (<<) will modify both strings:

copy << "bar"
copy
=> "foobar"
original
=> "foobar"

while the += operator will modify the caller only (ignore changes from previous block).

copy += "bar"
copy
=> "foobar"
original
=> "foo"

It works the other way around as well:

original << "bar"
copy
=> "foobar"
original
=> "foobar"
