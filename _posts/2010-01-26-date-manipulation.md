---
layout: post
title: Date manipulation
date: '2010-01-26T12:28:50+01:00'
tags:
- ruby
- beginner
- intermediate
tumblr_url: http://rubyquicktips.com/post/354231466/date-manipulation
---
You can add or subtract days or month from a Date object:

+(n): add n number of days
-(n): subtract n number of days
>>(n): add n number of months
<<(n): subtract n number of months
Here are some examples:

$ irb
>> date = Date.today     # => #<Date: ...>
>> date.to_s
=> "2010-01-26"
>> tomorrow = date + 1   # => #<Date: ...>
>> tomorrow.to_s
=> "2010-01-27"
>> nextmonth = date >> 1 # => #<Date: ...>
>> nextmonth.to_s
=> "2010-02-26"


Read the documentation for a more precise description.
