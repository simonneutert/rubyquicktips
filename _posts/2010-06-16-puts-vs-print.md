---
layout: post
title: puts vs. print
date: '2010-06-16T20:00:00+02:00'
tags:
- ruby
- intermediate
tumblr_url: http://rubyquicktips.com/post/705199687/puts-vs-print
---
There is something a bit peculiar about the puts and print methods in Ruby. puts seems to flush immediately, and therefore shows up on $stdout right away. Take the code example below:

5.times {
  puts "."
  sleep 2
}


This functions exactly the way that you would expect. It places a single period on $stdout, followed by a two second pause for five iterations. puts inserts a new line character as well, so instead of placing each period on the same line, each one is on a new line. print does not insert the automatic newline sequence, so it would place each one on the same line. However, the code below does not function the way you would expect.

5.times {
  print "."
  sleep 2
}


The code above waits for 10 seconds and then prints all 5 periods. As it turns out, this is because the print method buffers the output. The easiest way to get around this (for a situation like the above) is to set the sync property on $stdout.

STDOUT.sync = true
5.times {
  print "."
  sleep 2
}


This sets $stdout to avoid buffering the input, which most modern operating systems do. If you find yourself in a situation where you need to have a small amount of output sent immediately to the screen, this is a good technique to utilize to serve this requirement.

This tip was originally published by Matt Berther on his blog.
