---
layout: post
title: Select from a Hash by value
date: '2010-05-18T20:00:00+02:00'
tags:
- ruby
- beginner
- intermediate
- submission
tumblr_url: http://rubyquicktips.com/post/610604769/select-from-a-hash-by-value
---
Say, we have a Hash with codes for colors:

COLOR = { :red => 1, :white => 2, :black => 3, :yellow => 4 }


…and we want to check which color belongs to number 3.

COLOR.invert[3]
#=> :black


This tip uses Hash#invert, which “returns a new hash, created by using hsh‘s values as keys, and the keys as values.”
