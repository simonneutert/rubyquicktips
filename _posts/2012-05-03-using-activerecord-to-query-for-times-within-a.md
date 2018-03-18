---
layout: post
title: Using ActiveRecord to query for times within a range
date: '2012-05-03T08:01:03+02:00'
tags:
- rubyonrails
tumblr_url: http://rubyquicktips.com/post/22308979539/using-activerecord-to-query-for-times-within-a
---
You can pass a range to query for records within that range:

hackerinspiration:



Just discovered this, something I wish I knew a LONG time ago.


  Album.where(:created_at => 2.days.ago..Time.now)


Which will generate the following SQL query (depending on the database):


  SELECT "albums".* FROM "albums" WHERE ("albums"."created_at" BETWEEN ''2012-04-28 11:10:22.780712'' AND ''2012-04-30 11:10:22.780907'')


