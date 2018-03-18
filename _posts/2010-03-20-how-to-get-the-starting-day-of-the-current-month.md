---
layout: post
title: How to get the starting day of the current month?
date: '2010-03-20T04:10:00+01:00'
tags:
- beginner
- ruby
- submission
tumblr_url: http://rubyquicktips.com/post/460099365/how-to-get-the-starting-day-of-the-current-month
---
In addition to calculate the last day of a month, here is one method to calculate the first day:

$ irb
today = Date.today
today.to_s
=> "2010-03-20"
start_date = Date.parse "#{today.year}-#{today.month}-01"
start_date.to_s
=> "2010-03-01"


Check out the documentation on Date#parse.

This tip was submitted by TechSlam.

How would you do it?
