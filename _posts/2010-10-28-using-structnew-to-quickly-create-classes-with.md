---
layout: post
title: Using Struct.new to quickly create classes with accessor methods
date: '2010-10-28T11:32:44+02:00'
tags:
- ruby
- submission
tumblr_url: http://rubyquicktips.com/post/1422387295/using-structnew-to-quickly-create-classes-with
---
You can use Struct.new to quickly create a custom class and inherit accessor methods and the to_s method.

class Office < Struct.new("Place", :coffee, :cigarettes)
end


Now you can do:

o = Office.new
o.coffee = true
o.to_s
=> "#<struct Office coffee=true, cigarettes=nil>"


Check out the Struct class.

This tip was submitted by Marco Campana.
