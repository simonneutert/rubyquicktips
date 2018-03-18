---
layout: post
title: content_for stores a block of markup in an identifier for later use
date: '2009-12-23T02:08:00+01:00'
tags:
- rubyonrails
- intermediate
tumblr_url: http://rubyquicktips.com/post/295900828/contentfor-stores-a-block-of-markup-in-an
---

  Calling content_for stores a block of markup in an identifier for later use. You can make subsequent calls to the stored content in other templates or the layout by passing the identifier as an argument to yield.


F.e. this is quite useful to set the title of your page depending on what view is displayed. In your view you write something like

<% content_for :title, "My title" %>


…and in your (application) layout you call yield inside the title tag:

<head>
  <title><%= yield :title %> | Application name</title>
</head>


Check out the complete documentation on content_for.
