---
layout: post
title: Find more than one ActiveRecord Object at a time
date: '2010-08-25T13:00:00+02:00'
tags:
- rubyonrails
tumblr_url: http://rubyquicktips.com/post/1008376558/find-more-than-one-activerecord-object-at-a-time
---
Everybody knows that you can retrieve an ActiveRecord object like this:

user = User.find(41)
=> #<User id: 41>


But did you know that you can pass multiple ids to the find method?

user = User.find(1, 2, 5)
=> [#<User id: 1>, #<User id: 2>, #<User id: 5>]


Principle of least surprise.
