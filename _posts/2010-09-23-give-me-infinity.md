---
layout: post
title: Give me Infinity
date: '2010-09-23T11:03:00+02:00'
tags:
- ruby
tumblr_url: http://rubyquicktips.com/post/1172123941/give-me-infinity
---
In Ruby, dividing a kind of Integer (e.g a Fixnum or Bignum) by 0 will result in a ZeroDivisionError. Make the divisor and/or the dividend a float, e.g. 1.0/0, 1/0.0, or 1.0/0.0 and an exception will not be raised, the quotient returned will be Infinity.

It can be quite useful, I used this today for some discount code, i.e. sometimes a discount should never be applied.

ruby-1.9.2-p0 > 1/0
ZeroDivisionError: divided by 0
    from (irb):1:in `/''
    from (irb):1
    from /Users/stevegraham/.rvm/rubies/ruby-1.9.2-p0/bin/irb:17:in `<main>''
ruby-1.9.2-p0 > 1/0.0
 => Infinity 


For negative Infinity, make the dividend or the divisor negative.
