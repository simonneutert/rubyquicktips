---
layout: post
title: Dynamic Scopes
date: '2011-08-29T08:00:05+02:00'
tags:
- rubyonrails
tumblr_url: http://rubyquicktips.com/post/9536974779/dynamic-scopes
---
Rails 2.3 introduced dynamic named scopes. Dynamic scopes are created for each attribute in your model, prefixed by scoped_by_:


  # A dynamic scope for a single attribute
Post.scoped_by_category(''tech'')
# => SELECT "posts".* FROM "posts" WHERE "posts"."category" = ''tech''

# One for multiple attributes, concatenated by ''_and_''
Post.scoped_by_category_and_author_id(''tech'', 1)
# => SELECT "posts".* FROM "posts" WHERE "posts"."category" = ''tech'' AND "posts"."author_id" = 1


The difference to dynamic finders (e.g. Post.find_by_category(''tech'')) is, that you can chain these together and add additional conditions - just like with any named scope:


  Post.scoped_by_category(''tech'').all(:select => "id, title")
# => SELECT id, title FROM "posts" WHERE "posts"."category" = ''tech''
