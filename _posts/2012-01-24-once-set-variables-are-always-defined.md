---
layout: post
title: Once set, variables are always defined
date: '2012-01-24T06:00:06+01:00'
tags:
- ruby
- submission
tumblr_url: http://rubyquicktips.com/post/16394557495/once-set-variables-are-always-defined
---
When you set a variable in a section of code that is never executed, the variable will still be defined.


  if false
  a = ''whatever''
end

puts a
# => "nil"
# Does NOT raise ''NameError: undefined local variable or method `a'' for main:Object''


This post was submitted by Olivier El Mekki.
