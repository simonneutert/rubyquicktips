---
layout: post
title: Grep anything from your Enumerables
date: '2010-07-28T13:00:00+02:00'
tags:
- ruby
- intermediate
- advanced
- submission
tumblr_url: http://rubyquicktips.com/post/870337608/grep-anything-from-your-enumerables
---
grep is a nice little method to select elements from an Enumerable that match a certain pattern. For example, you can look for string- or regular expression matches:

["Test", "Foo", "Bar"].grep ''Foo''
=> ["Foo"]

["Test", "Foo", "Bar"].grep /ba/i
=> ["Bar"]


You can even grep Numerics:

>> [nil, 1, "test", 2.5].grep Numeric
=> [1, 2.5]


…or Ranges:

>> [1,5,9,7].grep 5..7
=> [5, 7]


grep uses === to filter internally, so everything you can stuff to case..when will do.

This tip was submitted by codesnik.
