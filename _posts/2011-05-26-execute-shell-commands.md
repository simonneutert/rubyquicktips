---
layout: post
title: Execute shell commands
date: '2011-05-26T13:26:00+02:00'
tags:
- ruby
tumblr_url: http://rubyquicktips.com/post/5862861056/execute-shell-commands
---
There are a number of different ways to run shell commands from Ruby.

The exec command

Kernel#exec replaces the current process and runs the command:


  exec(''ls ~'')
# Nothing after this command is executed


This might be a bit impractical, so have a look at the other options.

Backticks or %x shortcut

Place your command inside backticks (`) or execute it within %x() and it will return the output of this command:


  `ls ~`
=> "Applications\nDesktop\nDocuments"
%x(ls ~)
=> "Applications\nDesktop\nDocuments"


The system command

Use Kernel#system and it will return true (command run successfully), false (unsuccessful) or nil (command execution failed):


  system(''ls ~'')
=> true


For all of these methods, you can access the PID and exit status of the unix process via the $? variable:


  $?.pid
=> 11988

$?.exitstatus
=> 0


There are more options and I recommend these resources for more details:

Ruby Kernel system, exec and %x
6 Ways to Run Shell Commands in Ruby
Calling Bash Commands From Ruby
