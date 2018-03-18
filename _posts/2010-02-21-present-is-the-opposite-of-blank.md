---
layout: post
title: present? is the opposite of blank?
date: '2010-02-21T18:00:00+01:00'
tags:
- rubyonrails
- beginner
- intermediate
tumblr_url: http://rubyquicktips.com/post/402892212/present-is-the-opposite-of-blank
---
present? is the negation of blank?:

address.present? == !address.blank? # => true


present? in the API documentation.

(via Marcin Michałowski’s and Travis’  comments)
