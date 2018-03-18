---
layout: post
title: Dynamic attribute-based finders
date: '2010-01-18T12:10:48+01:00'
tags:
- rubyonrails
- beginner
- intermediate
tumblr_url: http://rubyquicktips.com/post/340755295/dynamic-attribute-based-finders
---

  Dynamic attribute-based finders are a cleaner way of getting objects by simple queries without turning to SQL. They work by appending the name of an attribute to find_by_, find_last_by_, or find_all_by_, so you get finders like Person.find_by_user_name, Person.find_all_by_last_name, and Payment.find_by_transaction_id.


So, instead of writing

Person.find(:all, :conditions => ["last_name = ?", last_name])


…you just do

Person.find_all_by_last_name(last_name)


It is also possible to use multiple attributes by separating them with an _and_:

Person.find_by_user_name_and_password
Payment.find_by_purchaser_and_state_and_country


Taken from the ActiveRecord::Base documentation.
