---
layout: post
title: all? and any?
date: '2009-12-10T09:52:00+01:00'
tags:
- all?
- any?
- array
- beginner
- enumerable
- hash
- intermediate
- ruby
tumblr_url: http://rubyquicktips.com/post/277330553/all-and-any
---
With all? and any? you can check, if all or any elements of an Array or Hash (or any other class that includes the Enumerable module) match a certain criteria. The result is either true or false.

%w{ ant bear cat}.all? {|word| word.length >= 3} #=> true
%w{ ant bear cat}.all? {|word| word.length >= 4} #=> false
[ nil, true, 99 ].all?                           #=> false

%w{ ant bear cat}.any? {|word| word.length >= 3} #=> true
%w{ ant bear cat}.any? {|word| word.length >= 4} #=> true
[ nil, true, 99 ].any?                           #=> true


All examples taken from the Ruby rdoc documentation.
