---
layout: post
title: Redo vs. Retry
date: '2010-09-15T00:00:00+02:00'
tags:
- Ruby
- beginner
tumblr_url: http://rubyquicktips.com/post/1122838559/redo-vs-retry
---
redo and retry are both used to re-execute parts of a loop. But they differ in how much they re-execute: redo only repeats the current iteration, while retry repeats the whole loop from the start.

redo example:

(0..5).each do |i|
  puts "Value: #{i}"
  redo if i > 2
end


The result shows, that only the last iteration is repeated:

Value: 0
Value: 1
Value: 2
Value: 3
Value: 3
Value: 3
# ... this is an infinite loop


retry example:

(0..5).each do |i|
  puts "Value: #{i}"
  retry if i > 2
end


As you can see, the whole loop starts from the beginning after a retry:

Value: 0
Value: 1
Value: 2
Value: 3
Value: 0
Value: 1
Value: 2
# ... this is an infinite loop, too


(via Ruby Loops)
