---
layout: post
title: Quick Hash to a URL Query trick
date: '2012-08-18T11:03:44+02:00'
tags:
- ruby
- rubyonrails
- submission
tumblr_url: http://rubyquicktips.com/post/29682077100/quick-hash-to-a-url-query-trick
---
Got a hash of values you want to convert into a url query string? Use the to_query method:


  "http://www.example.com?" + { language: "ruby", status: "awesome" }.to_query
# => "http://www.example.com?language=ruby&status=awesome" 


Want to do it in reverse? Use CGI.parse:


  require ''cgi'' # Only needed for IRB, Rails already has this loaded
CGI::parse "language=ruby&status=awesome"
# => {"language"=>["ruby"], "status"=>["awesome"]} 


Both methods support nested values.

This tip was submitted by Victor Solis.
