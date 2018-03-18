---
layout: post
title: Display ActiveRecord generated SQL queries in the console
date: '2009-12-21T05:51:00+01:00'
tags:
- ActiveRecord
- SQL
- console
- query
- rubyonrails
- intermediate
tumblr_url: http://rubyquicktips.com/post/292826666/display-activerecord-generated-sql-queries-in-the
---
If you want the console to display the SQL query that ActiveRecord executes just do the following (before you do anything else in the console):

$ script/console
>> ActiveRecord::Base.logger = Logger.new(STDOUT)
=> #<Logger:0x10322d6d0 ...>
>> User.first
User Load (3.3ms)   SELECT * FROM "users" ORDER BY last_name, first_name ASC LIMIT 1


Each call to ActiveRecord now logs all of its activity to STDOUT (e.g., the console), via your custom logger instance.

(via Jamis Buck)
