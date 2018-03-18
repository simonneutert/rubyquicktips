---
layout: post
title: Shorter render statement for partials
date: '2010-01-04T03:01:00+01:00'
tags:
- partials
- rubyonrails
- beginner
- intermediate
tumblr_url: http://rubyquicktips.com/post/315539148/shorter-render-statement-for-partials
---
From Rails 2.3 on

render :partial => "p", :locals => { :x => 1 }


can be written as

render "p", :x => 1


(via DHH)
