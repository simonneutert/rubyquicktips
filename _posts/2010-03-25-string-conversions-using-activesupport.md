---
layout: post
title: String conversions using ActiveSupport
date: '2010-03-25T18:00:00+01:00'
tags:
- rubyonrails
- beginner
tumblr_url: http://rubyquicktips.com/post/472808699/string-conversions-using-activesupport
---
ActiveSupport adds some methods to convert strings into dates/times. It’s very nice, take a look.

Instead of

>> Date.parse(''2010-01-12'')
=> Tue, 12 Jan 2010


you can do:

>> ''2010-01-12''.to_date
=> Tue, 12 Jan 2010


It’s more intuitive and readable!

Check out the api docs.
