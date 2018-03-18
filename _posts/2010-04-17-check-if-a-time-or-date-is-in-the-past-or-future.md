---
layout: post
title: Check if a time or date is in the past or future
date: '2010-04-17T08:55:04+02:00'
tags:
- beginner
- rubyonrails
- submission
tumblr_url: http://rubyquicktips.com/post/527621930/check-if-a-time-or-date-is-in-the-past-or-future
---
ActiveSupport adds convenient methods for checking if a given time or date is in the future or past.

>> time = 2.hours.ago
>> time.past?
=> true
>> time.future?
=> false


Check out the api docs

This tip was submitted by Michał Łomnicki.
