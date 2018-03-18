---
layout: post
title: Halt execution with sleep
date: '2010-04-12T09:33:00+02:00'
tags:
- ruby
- intermediate
tumblr_url: http://rubyquicktips.com/post/515189266/halt-execution-with-sleep
---
If you want to halt execution of your code for a certain time span, you can use Kernel#sleep to do so:

5.times do
  puts Time.now.strftime("%H:%M:%S")
  sleep 1
end


You pass the number of seconds as the parameter, which can also be a Float. So, our example produces one output every second:

12:35:21
12:35:22
12:35:23
12:35:24
12:35:25
=> 5


Here are the API docs on sleep.
