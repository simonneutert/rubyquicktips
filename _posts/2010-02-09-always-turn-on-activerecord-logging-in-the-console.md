---
layout: post
title: Always turn on ActiveRecord logging in the console
date: '2010-02-09T11:19:00+01:00'
tags:
- rubyonrails
- intermediate
tumblr_url: http://rubyquicktips.com/post/379756937/always-turn-on-activerecord-logging-in-the-console
---
Remember that you can turn on ActiveRecord logging for the console and see what SQL-query is executed?
Here’s a statement you can put in your environment.rb file (or in one specific environment config file - such as development.rb) to have it turned on permanently:

if "irb" == $0
  ActiveRecord::Base.logger = Logger.new(STDOUT)
end


I think it makes most sense to put it in development.rb and have logging always enabled for the console while developing.

(via Jamis Buck’s own comment on his post)
