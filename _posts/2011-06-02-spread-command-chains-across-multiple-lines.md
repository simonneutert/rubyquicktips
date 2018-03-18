---
layout: post
title: Spread command chains across multiple lines
date: '2011-06-02T12:31:00+02:00'
tags:
- ruby
tumblr_url: http://rubyquicktips.com/post/6103761205/spread-command-chains-across-multiple-lines
---
Ruby’s syntax allows you to spread command chains across multiple lines:


  puts "You can do a lot with this in one line".reverse.sub(''eno'', ''elpitlum'').sub('' htiw tol a'', '''').reverse.<< ''s, too!''


…can also be written like this:


  puts "You can do a lot with this in one line".
reverse.
sub(''eno'', ''elpitlum'').
sub('' htiw tol a'', '''').
reverse.
<< ''s, too!''


In Ruby < 1.9 you have to place the dot at the end of the line, like shown in the example above. From Ruby 1.9 on, you can also place the dot at the  beginning of the next line, right before the next command call.
