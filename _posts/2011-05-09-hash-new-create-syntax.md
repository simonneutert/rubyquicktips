---
layout: post
title: 'Hash: new create syntax'
date: '2011-05-09T10:00:53+02:00'
tags:
- ruby
- submission
tumblr_url: http://rubyquicktips.com/post/5329875867/hash-new-create-syntax
---
Additional to the syntax for creating hashes we all know:


  hash = { :first => "ruby", :second => "rails" }
# => {:first=>"ruby", :second=>"rails"}

hash[:first] # => "ruby"


…Ruby > 1.9.1 adds support for another syntax:


  hash = { first: "ruby", second: "rails" }
# => {:first=>"ruby", :second=>"rails"}

# you still have to access a value via a symbol
hash[:second] # => "rails"
hash[second]  # NameError
