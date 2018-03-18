---
layout: post
title: Next, please!
date: '2010-09-13T08:00:00+02:00'
tags:
- ruby
- beginner
tumblr_url: http://rubyquicktips.com/post/1114012305/next-please
---
The next command will jump to the next iteration of the most internal loop:

(0..5).each do |i|
  next if i < 2
  puts "Value: #{i}"
end


The output looks like this:

Value: 2
Value: 3
Value: 4
Value: 5


(via Ruby Loops)
