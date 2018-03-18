---
layout: post
title: 'Console tip: retrieve the last return value with underscore'
date: '2010-01-19T12:21:41+01:00'
tags:
- ruby
- rubyonrails
- intermediate
tumblr_url: http://rubyquicktips.com/post/342527837/console-tip-retrieve-the-last-return-value-with
---
In IRB you can retrieve the last return value from a command by using the underscore _ sign:

$ irb
>> 2*3
=> 6
>> _ + 7
=> 13
>> _
=> 13


This also works in the Rails console:

$ script/console
>> User.first
=> #<User id: 7, first_name ...
>> user = _
=> #<User id: 7, first_name ...
>> user
=> #<User id: 7, first_name ...


This is quite useful, when you forgot to assign the return value of an expression to a variable.
