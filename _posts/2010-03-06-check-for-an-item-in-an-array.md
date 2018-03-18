---
layout: post
title: Check for an item in an array
date: '2010-03-06T18:00:00+01:00'
tags:
- ruby
- beginner
- submission
tumblr_url: http://rubyquicktips.com/post/430483706/check-for-an-item-in-an-array
---
Use the include? method to check if your array contains the supplied object:

>> [''Cat'', ''Dog'', ''Bird''].include? ''Dog''=> true>> [''Cat'', ''Dog'', ''Bird''].include? ''Rat''=> false

Check out the documentation on include?.
There are more object types that define the include? method: f.e. String and Hash.

This tip was submitted by TechSlam.
