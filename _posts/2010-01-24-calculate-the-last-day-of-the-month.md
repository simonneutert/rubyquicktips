---
layout: post
title: Calculate the last day of the month
date: '2010-01-24T12:20:49+01:00'
tags:
- ruby
- beginner
- intermediate
tumblr_url: http://rubyquicktips.com/post/350625885/calculate-the-last-day-of-the-month
---
With Date.civil(y, m, d) (or its alias .new(y, m, d)), you can create a new Date object. The values for day (d) and month (m) can be negative in which case they count backwards from the end of the year and the end of the month respectively.

>> Date.civil(2010, 02, -1)
=> Sun, 28 Feb 2010
>> Date.civil(2010, -1, -5)
=> Mon, 27 Dec 2010


See the documentation on civil method.
