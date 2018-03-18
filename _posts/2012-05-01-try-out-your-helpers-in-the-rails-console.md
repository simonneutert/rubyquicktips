---
layout: post
title: Try out your helpers in the Rails console
date: '2012-05-01T08:01:08+02:00'
tags:
- rubyonrails
tumblr_url: http://rubyquicktips.com/post/22179967351/try-out-your-helpers-in-the-rails-console
---
Ever wanted to try out any of Rails’ view helper methods in the console? Just include ActionView::Helpers after starting the Rails console:


  include ActionView::Helpers
# => Object
text_field(:post, :title)
# => "<input id=\"post_title\" name=\"post[title]\" size=\"30\" type=\"text\" />"
