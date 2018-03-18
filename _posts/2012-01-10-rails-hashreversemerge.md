---
layout: post
title: Rails' Hash#reverse_merge
date: '2012-01-10T06:00:05+01:00'
tags:
- rubyonrails
tumblr_url: http://rubyquicktips.com/post/15606878757/rails-hashreversemerge
---
Ruby’s Hash#merge combines two Hashes, where the second Hash replaces values with the same key of the calling Hash.

Rails adds the method Hash#reverse_merge which keeps the contents of the caller. This gives you - for example - an elegant way to specify default values for an optional argument Hash:


  def my_method(options = {})
  options = options.reverse_merge(:option1 => "foo", :option2 => "bar")
  # If you pass in options with the :option1 and :option2 keys,
  # their values will NOT be overwritten.
  # If you leave option1 and option2 out, the defaults passed
  # to reverse_merge will be inserted.
  # actual method implementation here
end
