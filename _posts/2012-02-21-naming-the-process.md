---
layout: post
title: Naming the Process
date: '2012-02-21T06:00:05+01:00'
tags:
- ruby
- submission
tumblr_url: http://rubyquicktips.com/post/17995782789/naming-the-process
---
You can set the name of the current Ruby process, the one that you would see from the ps command for example.
Simply assign a string to the global variable $PROGRAM_NAME:


  $PROGRAM_NAME = ''Hello from Rubyland!''
puts $0 # This is an alias for the same thing.


This is a great way for long running scripts or daemon processes to communicate status information to people who are looking in on them.


  5.times do |i|
  $PROGRAM_NAME = "Ruby Quicktips Example: On iteration #{i}"
  sleep 5 # I''m really busy!!
end


Execute something like this in your terminal:


  ps x | grep Quicktips


This tip was submitted by Jesse Storimer.
