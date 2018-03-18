---
layout: post
title: Easily swap two variables’ values
date: '2010-02-12T00:43:17+01:00'
tags:
- ruby
- beginner
- intermediate
tumblr_url: http://rubyquicktips.com/post/384502538/easily-swap-two-variables-values
---
In Ruby, you can easily swap values of two variables without the need for a temporary third variable:

x,y = y,x


This is called ‘Parallel Assignment’.
Can’t believe it? I had to test it myself, too:

$ irb
>> x = 5
=> 5
>> y = 10
=> 10
>> x,y = y,x
=> [10, 5]
>> x
=> 10
>> y
=> 5


Check the Pickaxe for more about Parallel Assignment.

This post was ''manually’ reblogged from 5v3n.
