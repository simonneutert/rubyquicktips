---
layout: post
title: Catch all routes
date: '2010-06-11T07:53:09+02:00'
tags:
- beginner
- rubyonrails
- submission
tumblr_url: http://rubyquicktips.com/post/686091434/catch-all-routes
---
To catch all routes and get rid of the “No route matches” error, you can add something like the following to config/routes.rb:

map.connect ''*path'', :controller => "pages", :action => "show"


This tip was submitted by Özgün Koyun.
