---
layout: post
title: Two Ruby tricks using method chaining and Procs
date: '2012-04-04T10:02:27+02:00'
tags:
- ruby
tumblr_url: http://rubyquicktips.com/post/20458300054/two-ruby-tricks-using-method-chaining-and-procs
---

  [1,2,3].each_with_object(1).map(&:+)
# => [2, 3, 4]

# Same outcome, even shorter
[1, 2, 3].map(&1.method(:+))
# => [2, 3, 4]


In his blog post In Ruby, &method passes you!, Andrew Grimm explains how this all works.

Both snippets via Peter Cooper.
