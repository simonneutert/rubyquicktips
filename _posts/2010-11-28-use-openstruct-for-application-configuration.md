---
layout: post
title: Use OpenStruct for application configuration variables
date: '2010-11-28T22:00:07+01:00'
tags:
- rubyonrails
- ruby
- submission
tumblr_url: http://rubyquicktips.com/post/1718141794/use-openstruct-for-application-configuration
---
Every rails app I’ve ever built needs some sort of configuration, and I seem to be solving this problem a different way every time, which really bothers me. Today I learned about a new class called OpenStruct. Here’s how you could use it.

# in app_root/config/initializers/app_config.rb

require ''ostruct''

AppConfig = OpenStruct.new

AppConfig.default_email = "no-reply@example.com"
AppConfig.api_url = "staging.someapi.com"


Now you have a neat way of defining global configuration variables without using constants or defining custom classes.

This tip was submitted by Jon Druse.
