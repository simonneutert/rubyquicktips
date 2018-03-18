---
layout: post
title: Convert anything to boolean
date: '2010-05-09T13:08:39+02:00'
tags:
- rubyonrails
- ruby
- intermediate
- submission
tumblr_url: http://rubyquicktips.com/post/583755021/convert-anything-to-boolean
---
Just add !! (a.k.a. the double bang operator) before any statement:

>> @document = Document.new
=> <Document id: nil, title: nil>

>> @document.title
=> nil
>> !!@document.title
=> false

>> @document.title = "My new document"
>> !!@document.title
=> true


In Rails, you can use the name of your attribute followed by a question mark:

>> @document.title?
=> true

>> @document.title = nil
>> @document.title?
=> false


If you want to read more about this, I recommend the following blogposts and their comments:

bangbang your nil is dead
Ruby !!
!! in Ruby
This tip was submitted by Vladimir Rybas.
