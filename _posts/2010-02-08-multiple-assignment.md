---
layout: post
title: Multiple Assignment
date: '2010-02-08T11:06:46+01:00'
tags:
- intermediate
- ruby
- beginner
tumblr_url: http://rubyquicktips.com/post/377861025/multiple-assignment
---
You can assign multiple values to multiple variables like this:

foo, bar = [1, 2]  # foo = 1; bar = 2
foo, bar = 1, 2    # foo = 1; bar = 2
foo, bar = 1       # foo = 1; bar = nil


F.e. this can be useful for splitting names:

>> name = "Joe Bloggs"
=> "Joe Bloggs"
>> firstname, lastname = name.split
=> ["Joe", "Bloggs"]
>> firstname
=> "Joe"
>> lastname
=> "Bloggs"
>> name
=> "Joe Bloggs"


Read more on assignment in Ruby.
