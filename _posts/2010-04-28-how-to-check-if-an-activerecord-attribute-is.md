---
layout: post
title: How to check if an ActiveRecord attribute is present
date: '2010-04-28T13:38:45+02:00'
tags:
- rubyonrails
- beginner
tumblr_url: http://rubyquicktips.com/post/555718942/how-to-check-if-an-activerecord-attribute-is
---
You can use attribute names followed by question mark. Let’s assume there is an ActiveRecord class Person, having first_name and last_name as attributes.

p = Person.new
p.first_name = ''Mike''

p.first_name? # => true
p.last_name? # => false


Tip reblogged from milandobrota.
