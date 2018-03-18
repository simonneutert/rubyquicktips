---
layout: post
title: Rails 3, Bundler and forking gems
date: '2011-08-24T08:00:05+02:00'
tags:
- rubyonrails
- submission
tumblr_url: http://rubyquicktips.com/post/9325616377/rails-3-bundler-and-forking-gems
---
Did you know you can specify a Github repo or custom path to a gem in your Gemfile? Either stay up to date with bleeding edge changes or fork your own version. In your Gemfile:


  # Referencing Github
gem ''sg-ruby'', :git => ''git://github.com/simplegeo/simplegeo-ruby.git''

# Referencing local copy
gem ''sg-ruby'', :path => "/Users/user/gems/simplegeo-ruby"
