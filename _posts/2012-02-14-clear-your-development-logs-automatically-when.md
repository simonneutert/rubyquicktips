---
layout: post
title: Clear your development logs automatically when they are too large
date: '2012-02-14T06:00:00+01:00'
tags:
- rubyonrails
- submission
tumblr_url: http://rubyquicktips.com/post/17594543524/clear-your-development-logs-automatically-when
---
This snippet simply clears your logs when they are too large. Every time you run rails server or rails console it checks log sizes and clears the logs for you if necessary.


  # config/initializers/clear_logs.rb

if Rails.env.development?
  MAX_LOG_SIZE = 2.megabytes
  
  logs = File.join(Rails.root, ''log'', ''*.log'')
  if Dir[logs].any? {|log| File.size?(log).to_i > MAX_LOG_SIZE }
    $stdout.puts "Runing rake log:clear"
    `rake log:clear`
  end 
end


This tip was submitted by pahanix.
