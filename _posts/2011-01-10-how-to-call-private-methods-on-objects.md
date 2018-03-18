---
layout: post
title: How to Call Private Methods On Objects
date: '2011-01-10T08:00:00+01:00'
tags:
- ruby
tumblr_url: http://rubyquicktips.com/post/2681282667/how-to-call-private-methods-on-objects
---
Calling private methods can for example be useful in unit testing to increase the code coverage.Object#send gives you access to all methods of a particular object (even protected and private ones).


  obj.send(:method [, args...])


In case send method has been overwritten, you can also use its aliased version __send__.
