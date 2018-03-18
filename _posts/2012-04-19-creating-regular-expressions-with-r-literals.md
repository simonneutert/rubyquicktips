---
layout: post
title: Creating regular expressions with r{} literals
date: '2012-04-19T08:01:13+02:00'
tags:
- ruby
tumblr_url: http://rubyquicktips.com/post/21370656103/creating-regular-expressions-with-r-literals
---
Creating a regular expression using the r{} literals can for example be helpful when matching URLs, because you don’t have to escape slashes:


  url = "http://example.com/"

# /../ literals:
url.match /http:\/\/example\.com\//
# => #<MatchData "http://example.com/">

# %r{} literals:
url.match %r{http://example\.com/}
# => #<MatchData "http://example.com/">
