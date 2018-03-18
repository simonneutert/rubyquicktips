---
layout: post
title: Check if your associations have been eager loaded
date: '2011-06-13T00:11:06+02:00'
tags:
- rubyonrails
tumblr_url: http://rubyquicktips.com/post/6467112014/check-if-your-associations-have-been-eager-loaded
---
If you want to check if associations of an object have been eager loaded, use the loaded? method:


  @blogpost = Post.includes(:comments).find(1)
@blogpost.comments.loaded?
=> true

@blogpost = Post.find(1)
@blogpost.comments.loaded?
=> false


This might for example be useful to test eager loading in your tests.
