---
layout: post
title: Using "try" with a hash to check existence of a key
date: '2011-04-14T08:00:00+02:00'
tags:
- rubyonrails
- submission
tumblr_url: http://rubyquicktips.com/post/4601358354/using-try-with-a-hash-to-check-existence-of-a
---
The try method is awesome. Check the documentation.
It is usually used to call a method on an object if it exists, or return nil if it doesn’t.

But sometimes, it is not used with hashes, but this also works perfectly:


  params[:search] ? params[:search][:name] : nil

# Can also be written as...
params[:search].try(:[],:name)


Clean!

This tip was submitted by Miguel Camba.
