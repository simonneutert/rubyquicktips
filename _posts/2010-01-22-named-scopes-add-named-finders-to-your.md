---
layout: post
title: 'Named Scopes: add named finders to your ActiveRecord Model'
date: '2010-01-22T12:21:00+01:00'
tags:
- rubyonrails
- intermediate
tumblr_url: http://rubyquicktips.com/post/347266401/named-scopes-add-named-finders-to-your
---
With a ‘named scope’, you can add reusable ActiveRecord find methods to your model.
So instead of writing this in your controller, every time you need it…

User.find(:all, :conditions => { :active => true }, :order => "first_name, last_name ASC")


…you can add a named scope to your User model that represents this find statement:

class User < ActiveRecord::Base
  named_scope :active, :conditions => { :active => true }, :order => "first_name, last_name ASC"
end


Now, you can use this named scope by calling it from within your controller like this:

User.active


Named scopes make your (controller) code more readable and shorter.
A named scope can take all options a find statement can. And - as a plus - you can even chain named scopes, which is particularly awesome.
There’s a whole lot more you can do. Check out Ryan Daigle’s introduction and the documentation.
