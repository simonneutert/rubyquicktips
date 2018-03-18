---
layout: post
title: Find or Create an object in one command
date: '2010-01-20T12:21:48+01:00'
tags:
- rubyonrails
- beginner
- intermediate
tumblr_url: http://rubyquicktips.com/post/344181578/find-or-create-an-object-in-one-command
---
The find_or_create_by_ dynamic finder will return the object if it already exists and otherwise creates it, then returns it:

# No ''Summer'' tag exists
Tag.find_or_create_by_name("Summer") # equal to Tag.create(:name => "Summer")

# Now the ''Summer'' tag does exist
Tag.find_or_create_by_name("Summer") # equal to Tag.find_by_name("Summer")


There’s also a find_or_initialize_by finder if you want to return a new record without saving it first:

# No ''Winter'' tag exists
winter = Tag.find_or_initialize_by_name("Winter")
winter.new_record? # true


Everything taken from the Rails API.
