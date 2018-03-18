---
layout: post
title: Split a string with 'split'
date: '2010-01-21T12:21:47+01:00'
tags:
- ruby
- beginner
tumblr_url: http://rubyquicktips.com/post/345823279/split-a-string-with-split
---
To split a string at a a given delimiter, use the split method. The default delimiter is the space ’ ’, and an array of the words is returned.

"A string to split".split # => ["A", "string", "to", "split"]
"tag1,tag2,tag3".split('','') # => ["tag1", "tag2", "tag3"]


Ruby Documentation.
