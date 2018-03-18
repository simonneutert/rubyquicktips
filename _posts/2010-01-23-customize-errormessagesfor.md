---
layout: post
title: Customize error_messages_for
date: '2010-01-23T12:20:48+01:00'
tags:
- rubyonrails
- beginner
- intermediate
tumblr_url: http://rubyquicktips.com/post/348876721/customize-errormessagesfor
---
Did you know that error_messages_for takes a whole bunch of options for customization?

<%= error_messages_for :employee,
                       :class => "flash error",
                       :header_tag => "h4",
                       :header_message => "Sorry, the employee couldn''t be created" %>


The options for the <div> that is returned include :header_tag, :id, :class, :header_message, :message and more.

Check out the docs on :error_messages_for for more.
