---
layout: post
title: Array#first and Array#last parameters
date: '2010-12-14T11:07:08+01:00'
tags:
- ruby
- submission
tumblr_url: http://rubyquicktips.com/post/2311239580/arrayfirst-and-arraylast-parameters
---
Did you know you can pass a number parameter to Array#first and Array#last?

x = [1,2,3,4,5,6,7,8,9,10]

x.first 5 
=> [1,2,3,4,5] 

x.last 2 
=> [9,10] 


This tip was submitted by Alfred Nagy.
