---
layout: post
title: Rails 3 Validation Shortcut
date: '2011-02-24T06:00:00+01:00'
tags:
- rubyonrails
- submission
tumblr_url: http://rubyquicktips.com/post/3477822283/rails-3-validation-shortcut
---
In Rails 2 the only way to add multiple validations to a field is through separate validate statements:


  validates_presence_of :title
validates_length_of :title, :maximum => 30


Rails 3 simplifies this process by adding a method called validates which is a “shortcut to all default validators”. Using the validates method your code will look like this:


  validates(:title, :presence => true, :length => {:maximum => 30})


You can find more information about this method in the API documentation here.
