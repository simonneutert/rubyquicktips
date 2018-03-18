---
layout: post
title: Deep clone
date: '2010-11-26T05:24:54+01:00'
tags:
- ruby
- submission
tumblr_url: http://rubyquicktips.com/post/1687572267/deep-clone
---
Ruby comes with an Object#clone method that lets you copy objects. But this method makes a shallow copy, i.e. a duplicate without copying any referenced objects.

Object#clone:


  Produces a shallow copy of obj - the instance variables of obj are copied, but not the objects they reference.


If you need a deep clone of an object - i.e. a copy including referenced objects - the Marshal module is your friend:

deep_cloned = Marshal::load(Marshal.dump(origin))


This tip was submitted by Jaime Iniesta.
