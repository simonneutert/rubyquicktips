---
layout: post
title: Get the union of a set of sets using flatten and uniq
date: '2010-03-17T11:20:01+01:00'
tags:
- ruby
- beginner
- submission
tumblr_url: http://rubyquicktips.com/post/454188120/get-the-union-of-a-set-of-sets-using-flatten-and
---
Instead of using inject and the pipe operator (|) to get the union of a set of sets, you can also use flatten and uniq:

a = [[1,2,3],[2,3,4],[3,4,5]]
a.flatten.uniq # => [1, 2, 3, 4, 5]


Check out the API documentation for flatten and uniq.

This tips was submitted by Aqab Bin Talal and also pointed out by doesterr.
