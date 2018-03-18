---
layout: post
title: Method chaining with inject
date: '2012-03-15T06:02:05+01:00'
tags:
- ruby
- submission
tumblr_url: http://rubyquicktips.com/post/19332576850/method-chaining-with-inject
---
Aim: perform a method chaining based on hash

Required operation:


  ErrorLog.event_eq([3, 7]).subdomain_like("default").user_id_eq(100)



Given:


  search_opts = { :event_eq => [3, 7], :subdomain_like => "default", :user_id_eq => 100 }



Solution:


  search_opts.inject(ErrorLog) { |memo, (k, v)| memo.send(k, v) }


This tip was submitted by sumskyi.
