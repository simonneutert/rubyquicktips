---
layout: post
title: Enumerable#reverse_each
date: '2012-01-12T06:00:06+01:00'
tags:
- ruby
tumblr_url: http://rubyquicktips.com/post/15710561322/enumerablereverseeach
---
reverse_each is like Array#each or Hash#each - in reverse:


  a = [1,2,3]

a.each { |v| puts v }
# 1
# 2
# 3
a.reverse_each { |v| puts v }
# 3
# 2
# 1
