---
layout: post
title: Give it a try!
date: '2010-02-10T23:18:23+01:00'
tags:
- rubyonrails
- intermediate
tumblr_url: http://rubyquicktips.com/post/382482752/give-it-a-try
---
As of Rails 2.3, there is a handy new try method on objects, which allows you to invoke a method on a possibly nil object without throwing a NoMethodError. This saves you the trouble of checking if your object is nil before accessing a method.

For example, previously you’d need to do something like this:

article = Article.find_by_title("My Article")
unless article.nil? 
  article.body
end


With try you can skip the nil? check and do the following:

Article.find_by_title("My Article").try(:body) => #body or nil


Check out the documentation on try.

This post was ‘manually’ reblogged from michaelbulat.
