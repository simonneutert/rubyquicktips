---
layout: post
title: Conditional Validation using with_options to improve readability
date: '2010-02-25T18:00:00+01:00'
tags:
- rubyonrails
- intermediate
- submission
tumblr_url: http://rubyquicktips.com/post/411400798/conditional-validation-using-withoptions-to
---
When you have a model that requires additional information, if a certain condition is met and you need to validate this attribute, this little trick can help.

Say we have a user model that needs to validate the truck_serial attribute if the user has the role of driver:

class User < ActiveRecord::Base
  has_many :roles

  # Normal Validations 
  validates_presence_of   :user_name
  validates_uniqueness_of :user_name

  with_options :if => :driver? do |driver|
    driver.validates_presence_of :truck_serial
    driver.validates_length_of :truck_serial, :maximum => 30
  end

  def driver?
    roles.any? { |role| role.name == "driver" }
  end 
end  


We are basically combining the ActiveSupport Object#with_options and ActiveRecord’s conditional validation.

This tip was submitted by exceptionz.
