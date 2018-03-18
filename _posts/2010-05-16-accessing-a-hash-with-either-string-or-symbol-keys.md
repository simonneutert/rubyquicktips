---
layout: post
title: Accessing a hash with either string or symbol keys
date: '2010-05-16T11:13:23+02:00'
tags:
- beginner
- ruby
- rubyonrails
- intermediate
- submission
tumblr_url: http://rubyquicktips.com/post/603292403/accessing-a-hash-with-either-string-or-symbol-keys
---
For a normal Ruby hash, the following code is true:

x = {"key1" => "value1"}
x["key1"] #=> "value1"
x[:key1] #=> nil


What if we want to use either x[:key1] or x["key1"] and get the same result?
Rails gives us a new Hash called HashWithIndifferentAccess that does just that. If we have a normal hash and we want to convert it into HashWithIndifferentAccess, we do the following:

x = {"key1" => "val1"}
x = x.with_indifferent_access
x[:key1] #=> "val1"
x["key1"] #=> "val1"


To instantiate a HashWithIndifferentAccess from the beginning we do the following:

x = HashWithIndifferentAccess.new #=> {}


See the APIs for Ruby Hashes and Rails’ HashWithIndifferentAccess.

This tip was submitted by humanzz.
