---
layout: post
title: Prevent String#split from throwing away empty trailing elements
date: '2011-01-06T07:09:47+01:00'
tags:
- ruby
- submission
tumblr_url: http://rubyquicktips.com/post/2620098585/prevent-stringsplit-from-throwing-away-empty
---
The default behavior of String#split will throw away any trailing values if they are empty.

> "Hello,There,,".split('','') 
=> ["Hello", "There"]


If you want to keep those empty trailing elements, pass a negative number for the second (limit) parameter.

> "Hello,There,,".split('','', -1)
=> ["Hello", "There", "", ""]


This tip was submitted by two-bit-fool.
