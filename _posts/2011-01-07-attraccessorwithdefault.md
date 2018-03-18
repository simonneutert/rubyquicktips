---
layout: post
title: attr_accessor_with_default
date: '2011-01-07T04:00:00+01:00'
tags:
- rubyonrails
tumblr_url: http://rubyquicktips.com/post/2631578325/attraccessorwithdefault
---
Here’s a method I haven’t seen before: attr_accessor_with_default

This ActiveSupport method allows you to set a default value for an attribute accessor:


  class Person
  attr_accessor_with_default :age, 25
end

some_person.age # => 25

some_person.age = 26
some_person.age # => 26


You can even pass in a block.
