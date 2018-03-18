---
layout: post
title: Format a string from a Time object
date: '2011-04-11T08:00:00+02:00'
tags:
- ruby
- submission
tumblr_url: http://rubyquicktips.com/post/4517067210/format-a-string-from-a-time-object
---
If you only want to print the first day of the current month you can use the string formating method on a Time object:


  > Time.now.strftime("%Y-%m-1")
"2011-04-1"


The method can be used to print date in almost any format:


  > Time.now.strftime("%A %B %d or %a %e/%m")
=> "Monday April 11 or Mon 11/04"


Check out Time#strftime for a list of directives. Time is part of the core, so there is no need to require anything.

This tip was submitted by Aqab Bin Talal.
