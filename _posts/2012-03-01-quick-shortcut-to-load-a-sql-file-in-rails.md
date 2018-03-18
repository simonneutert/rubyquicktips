---
layout: post
title: Quick shortcut to load a SQL file in Rails
date: '2012-03-01T05:48:38+01:00'
tags:
- rubyonrails
- submission
tumblr_url: http://rubyquicktips.com/post/18538210197/quick-shortcut-to-load-a-sql-file-in-rails
---
You can easily load SQL files like this:


  rails db < path_to_sql_file.sql # Rails 3 
script/dbconsole < path_to_sql_file.sql # Rails 2
