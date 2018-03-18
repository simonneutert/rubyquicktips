---
layout: post
title: Converting between Hexadecimal and Fixnum
date: '2010-03-21T22:00:00+01:00'
tags:
- ruby
- intermediate
tumblr_url: http://rubyquicktips.com/post/464001793/converting-between-hexadecimal-and-fixnum
---
Ruby provides an easy way to convert between hexadecimal and decimal numbers, or any other base:

>> 255.to_s(16)
=> "ff"


or

>> ''ff''.to_i(16)
=> 255


Simple and beautiful.
