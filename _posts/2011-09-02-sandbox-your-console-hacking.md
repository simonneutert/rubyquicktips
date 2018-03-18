---
layout: post
title: Sandbox your console hacking
date: '2011-09-02T08:00:05+02:00'
tags:
- rubyonrails
tumblr_url: http://rubyquicktips.com/post/9697931867/sandbox-your-console-hacking
---
When you start you Rails console, you can add the --sandbox parameter and all you modifications to the database will be rolled back again when you exit the console.


  rails console --sandbox  # Rails 3
script/console --sandbox # Rails 2
