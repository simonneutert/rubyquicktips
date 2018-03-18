---
layout: post
title: Random choice - eh, I mean sample - of an array's elements
date: '2011-01-11T22:15:00+01:00'
tags:
- ruby
tumblr_url: http://rubyquicktips.com/post/2702240316/random-choice-eh-i-mean-sample-of-an-arrays
---
Need a randomly chosen element from an array? There’s a method for that!Array#choice (Ruby 1.8.7) or Array#sample (Ruby > 1.8.7):


  [1,2,3,4,5,6,7,8,9].choice
=> 5        
[1,2,3,4,5,6,7,8,9].sample
=> 8
[1,2,3,4,5,6,7,8,9].sample(3)
=> [3,8,9]


Thanks to everyone who mentioned these methods here and here.
