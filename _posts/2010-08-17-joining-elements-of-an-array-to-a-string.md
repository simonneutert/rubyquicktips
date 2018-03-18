---
layout: post
title: Joining elements of an Array to a String
date: '2010-08-17T13:30:00+02:00'
tags:
- ruby
- beginner
- submission
tumblr_url: http://rubyquicktips.com/post/966804843/joining-elements-of-an-array-to-a-string
---
Coming from Java, it’s likely you share my simple “for-each-loop”-fixation:

tags              = ["ruby", "rails", "java"]
concatenated_tags = ""

tags.each { |tag| concatenated_tags << "#{tag}, " }

concatenated_tags # => "ruby, rails, java, "

#now, remove the unnecessary comma and space at the end
concatenated_tags.chop!.chop! # => "ruby, rails, java"


Ruby Arrays have a far more sophisticated function to solve the problem. Just use the join method and you’re done:

concatenated_tags = tags.join('', '') # => "ruby, rails, java"


This tip was submitted by Sven Kräuter.
