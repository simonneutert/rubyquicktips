---
layout: post
title: Convert a number string in any base to a decimal number
date: '2012-04-11T14:10:14+02:00'
tags:
- ruby
tumblr_url: http://rubyquicktips.com/post/20899948441/convert-a-number-string-in-any-base-to-a-decimal
---
As Brich Thompson notes in the comments on “Convert between number bases easily”, you can also convert a number string in any base to a decimal number with the String#to_i method:


  "21".to_i     #=> 21 
"21".to_i(8)  #=> 17
"21".to_i(16) #=> 33
