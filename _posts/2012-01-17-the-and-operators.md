---
layout: post
title: The =~ and !~ operators
date: '2012-01-17T06:00:06+01:00'
tags:
- ruby
tumblr_url: http://rubyquicktips.com/post/15994276561/the-and-operators
---
The operator =~ matches a String against a regular expression pattern. It returns the position/index where the String was matched - or nil if no match was found:


  /Quick/ =~ "Ruby Quicktips"
# => 5

# Order does not matter
"Ruby Quicktips" =~ /Quick/
# => 5

"Ruby Quicktips" =~ /foo/
# => nil


Because it returns nil when no match is found, you can for example use this as a condition in if-statements:


  if "Ruby Quicktips" =~ /\s+/
  puts "The string contains at least one whitespace character."
end
# The string contains at least one whitespace character.
# => nil


To check the opposite, you can use the !~ operator:


  if "Ruby Quicktips" !~ /\d+/
  puts "The string does not contain any digits."
end
# The string does not contains any digits.
# => nil
