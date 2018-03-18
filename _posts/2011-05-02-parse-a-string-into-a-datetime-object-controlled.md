---
layout: post
title: Parse a string into a DateTime object. Controlled.
date: '2011-05-02T12:54:00+02:00'
tags:
- ruby
- rubyonrails
tumblr_url: http://rubyquicktips.com/post/5129310254/parse-a-string-into-a-datetime-object-controlled
---
Just as you can format a string from a Time object with Time#strftime, you can also parse a string in a defined format into a DateTime or Date object, using DateTime#strptime or Date#strptime respectively (Date#strptime only creates a date without the time, though).


  require ''date''

parsed_time = DateTime.strptime(''03/05/2010 14:25:00'', ''%d/%m/%Y %H:%M:%S'')

parsed_time.to_s
=> "2010-05-03T14:25:00+00:00"


See the docs for more info: DateTime#strptime and Date#strptime.
