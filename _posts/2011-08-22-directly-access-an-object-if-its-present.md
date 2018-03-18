---
layout: post
title: Directly access an object if it's present
date: '2011-08-22T12:27:02+02:00'
tags:
- rubyonrails
- submission
tumblr_url: http://rubyquicktips.com/post/9247085311/directly-access-an-object-if-its-present
---
If you want to access an object only if it’s present, you can use Rails’ Object#presence.
The API docs on presence have a good explanation:


  This is handy for any representation of objects where blank is the same as not present at all. For example, this simplifies a common check for HTTP POST/query parameters:



  state   = params[:state]   if params[:state].present?
country = params[:country] if params[:country].present?
region  = state || country || ''US''



  …becomes:



  region = params[:state].presence || params[:country].presence || ''US''
