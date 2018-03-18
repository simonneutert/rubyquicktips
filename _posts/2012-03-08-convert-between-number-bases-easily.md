---
layout: post
title: Convert between number bases easily
date: '2012-03-08T06:00:06+01:00'
tags:
- ruby
- submission
tumblr_url: http://rubyquicktips.com/post/18935873770/convert-between-number-bases-easily
---
It’s often a requirement in various projects to convert numbers from decimal to text representations of several other bases, such as hexadecimal or binary.
Did you know you can convert to any base from 2 to 36 in one line in Ruby?

Using the Fixnum#to_s method, you can quickly convert any Fixnum object to the textual format of another base:


  255.to_s(36) #=> "73"
255.to_s(16) #=> "ff"
255.to_s(2)  #=> "11111111"


This tip was submitted by Nathan Kleyn.
