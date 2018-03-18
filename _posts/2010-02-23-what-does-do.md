---
layout: post
title: What does ||= do?
date: '2010-02-23T18:00:00+01:00'
tags:
- ruby
- beginner
- intermediate
tumblr_url: http://rubyquicktips.com/post/407228844/what-does-do
---
In Ruby, the ||= acts as a qualifier where it will evaluate the code on the left.  If that evaluates to nil, then it will evaluate the code on the right and attempt to set the code on the left to the right’s result.  Example below:

puts @post
# => nil

@post ||= Post.find(1)
puts @post # => <Post id: 1, ...>


If you had already set the instance variable @post to a value, it would simply return that value. Otherwise it will return the post.

If I set @post previously, it will return whatever that is.

@post = "QuickTip"
puts @post  # => "QuickTip"

@post ||= Post.find(1)
puts @post  # => "QuickTip"


This was originally posted by Kyle Daigle on his blog (which is currently offline).
