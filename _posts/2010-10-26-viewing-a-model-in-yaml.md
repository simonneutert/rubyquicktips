---
layout: post
title: Viewing a model in YAML
date: '2010-10-26T09:21:17+02:00'
tags:
- beginner
- rubyonrails
- ruby
- submission
tumblr_url: http://rubyquicktips.com/post/1405061475/viewing-a-model-in-yaml
---
The default viewing of attributes, and their values, of a model instance in script/console is not friendly. Principally if this model has many attributes, like the below example:

> order = Order.last
> order
=> #<Order id:1069267068, completed_at: nil, adjustment_total: 0.00, number: "R678647441", created_at: "2010-03-29 18:55:11", token: "LhiLU2J8ouIGHMUrkFab", updated_at: "2010-03-29 18:55:11", total: 19.99, item_total: 19.99, user_id: nil, site_id: 1, credit_total: 0.00, state: "in_progress">


A cleaner way to show these data is with YAML format. To do it, just call the y method passing the model instance as parameter.

> order = Order.last
> y order
--- !ruby/object:Order
attributes:
  completed_at:
  adjustment_total: "0.00"
  number: R678647441
  created_at: 2010-03-29 18:55:11
  token: LhiLU2J8ouIGHMUrkFab
  updated_at: 2010-03-29 18:55:11
  total: "19.99"
  item_total: "19.99"
  id: "1069267068"
  user_id:
  site_id: "1"
  credit_total: "0.00"
  state: in_progress
attributes_cache: {}

=> nil


That also works fine showing association attributes:

> order = Order.last
> order.line_items
> y order
--- !ruby/object:Order
attributes:
  completed_at:
  adjustment_total: "0.00"
  number: R678647441
  created_at: 2010-03-29 18:55:11
  token: LhiLU2J8ouIGHMUrkFab
  [...]
attributes_cache: {}

line_items:
- !ruby/object:LineItem
  attributes:
    price: "19.99"
    created_at: 2010-03-29 18:55:11
    quantity: "1"
    updated_at: 2010-03-29 18:55:11
    order_id: "1069267068"
    id: "1071009856"
    variant_id: "489273655"
  attributes_cache: {}

=> nil


This tip was submitted by Prodis.
