---
layout: post
title: Inclusive and Exclusive Ranges
date: '2010-05-21T08:00:00+02:00'
tags:
- ruby
- beginner
- submission
tumblr_url: http://rubyquicktips.com/post/618419107/inclusive-and-exclusive-ranges
---
Use two dots between numbers to include both numbers in the range and three dots to exclude the latter.

(1..3).to_a => [1, 2, 3]
(1...3).to_a => [1, 2]


See more on ranges.
