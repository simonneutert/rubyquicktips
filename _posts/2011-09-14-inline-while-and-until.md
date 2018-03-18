---
layout: post
title: Inline While and Until
date: '2011-09-14T08:00:05+02:00'
tags:
- ruby
tumblr_url: http://rubyquicktips.com/post/10195036659/inline-while-and-until
---
Similar to if and unless, while and until can be used inline, too:


  round = 0
puts round += 1 until round > 9

round = 0
puts round += 1 while round < 10
