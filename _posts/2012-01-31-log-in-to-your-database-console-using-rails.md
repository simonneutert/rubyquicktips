---
layout: post
title: Log in to your database console using Rails
date: '2012-01-31T06:00:05+01:00'
tags:
- rubyonrails
- submission
tumblr_url: http://rubyquicktips.com/post/16805618862/log-in-to-your-database-console-using-rails
---
Instead of using the database-specific command to start your project’s database console, Rails provides one consistent interface for the most popular databases (MySQL, PostgreSQL and SQLite):


  script/dbconsole [RAILS_ENV] # Rails 2
rails dbconsole [RAILS_ENV] # Rails 3
rails db [RAILS_ENV] # Rails 3 alias
