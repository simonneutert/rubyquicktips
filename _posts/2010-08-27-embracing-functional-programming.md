---
layout: post
title: Embracing Functional Programming
date: '2010-08-27T10:00:00+02:00'
tags:
- ruby
- intermediate
- submission
tumblr_url: http://rubyquicktips.com/post/1018776470/embracing-functional-programming
---
Yehuda Katz posted a question on Twitter the other night: what’s the easiest way to get [“X::Y::Z”, “X::Y”, “X”] from “X::Y::Z” in Ruby?
I was determined to accomplish this with a nice application of functional programming. In other words, how can I accomplish this without running procedural code?

The first part is to split the string on ::, which is simple enough with the split command. Next, we obviously need to iterate, but neither ’each’ nor ’map’ give access to the other elements. Enter ’inject’.
By seeding inject with an empty array, we can build up the array by using the most recently added element. Behold, the finished product:

module_name = "X::Y::Z"
module_name.split(''::'').inject([]) { |memo,x| memo.unshift(memo.empty? ? x : "#{memo[0]}::#{x}") }
=> ["X::Y::Z", "X::Y", "X"]


See? No need to use procedural code. Easy to understand with zero side-effects.

Well, you might want to have a look at some old tips and the Ruby API docs:

Split a string with ‘split’
Inject your enumerables
Array#unshift in the API docs
This tip was submitted by Bradley Grzesiak.
