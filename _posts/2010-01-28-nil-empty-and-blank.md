---
layout: post
title: nil?, empty? and blank?
date: '2010-01-28T11:59:51+01:00'
tags:
- ruby
- rubyonrails
- beginner
tumblr_url: http://rubyquicktips.com/post/357739776/nil-empty-and-blank
---
In Ruby, you check with nil? if an object is nil:

article = nil
article.nil?  # => true


empty? checks if an element - like a string or an array f.e. - is empty:

# Array
[].empty?   #=> true
# String
"".empty?   #=> true


Rails adds the method blank? to the Object class:


  An object is blank if it‘s false, empty, or a whitespace string. For example, “”, “ ”, nil, [], and {} are blank.


This simplifies

if !address.nil? && !address.empty?


to

if !address.blank?


Documentation: nil?, empty? (String, Array) and blank?
