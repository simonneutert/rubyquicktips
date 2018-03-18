---
layout: post
title: Making sure that an options Hash contains certain keys only
date: '2010-04-14T13:00:00+02:00'
tags:
- rubyonrails
- intermediate
- submission
tumblr_url: http://rubyquicktips.com/post/520576133/making-sure-that-an-options-hash-contains-certain
---
It’s common to see Ruby methods that accept an options Hash - like Rails’ image_tag form helper f.e., which has the following signature:


  image_tag(source, options = {})


Sometimes when we write methods like this, we want to make sure that the options passed are limited to certain keys. The best way to do this is by using Hash#assert_valid_keys (Rails API docs link):


  def do_something(options = {})
  options.assert_valid_keys :x, :y
  # do the real something
end


This way we easily restrict the set of accepted options to only :x and :y. If the options contains any other keys, an ArgumentError will be raised.

This tip was submitted by humanzz.
