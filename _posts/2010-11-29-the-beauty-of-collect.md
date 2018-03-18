---
layout: post
title: The Beauty of Collect
date: '2010-11-29T04:04:06+01:00'
tags:
- ruby
- submission
tumblr_url: http://rubyquicktips.com/post/1722404379/the-beauty-of-collect
---
Being from c programming background, to get an array of some property from the objects, I used to write this in Ruby:

amount_array = []

for order in account.orders
  amount_array << order.amount.some_operation
end


While a much cleaner way is to use Array#collect:

amount_array = account.orders.collect { |order| order.amount.some_operation }


This tip was submitted by zerothabhishek.
