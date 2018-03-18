---
layout: post
title: Grep an object's available methods
date: '2011-02-18T14:58:00+01:00'
tags:
- ruby
- submission
tumblr_url: http://rubyquicktips.com/post/3360442904/grep-an-objects-available-methods
---
Because Object.methods returns an array, you can grep that just like in this tip about grepping anything from your enumerables.
For example, if you are looking for a particular method of an object, you can easily narrow down the results like this:


  Object.methods.grep /inspect/
=> ["inspect", "pretty_inspect", "pretty_print_inspect"]


This tip was submitted Adam Rogers.
