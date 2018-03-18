---
layout: post
title: 'Around Alias '
date: '2012-02-28T07:28:11+01:00'
tags:
- ruby
- submission
tumblr_url: http://rubyquicktips.com/post/18427759343/around-alias
---
You can write an Around Alias in three simple steps:

You alias a method.
You redefine it.
You call the old method from the new method.
Example:


  class String
  alias :orig_length :length

  def length
    "Length of string ''#{self}'' is: #{orig_length}"
  end  
end

"abc".length
#=> "Length of string ''abc'' is: 3"


This tip was submitted by Nimesh Nikum.
