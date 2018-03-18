---
layout: post
title: validates_length_of without validates_presence_of
date: '2010-05-25T02:46:22+02:00'
tags:
- rubyonrails
- intermediate
tumblr_url: http://rubyquicktips.com/post/629615295/validateslengthof-without-validatespresenceof
---
If you want to use validates_length_of without validates_presence_of, you have to specify the :allow_nil option. Otherwise the statement would also implicitly validate the presence:

validates_length_of :zipcode, :within => 0..10, :allow_nil => true


Check out the Rails API on validates_length_of.
