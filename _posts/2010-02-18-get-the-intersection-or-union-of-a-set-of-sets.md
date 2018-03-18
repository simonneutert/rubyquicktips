---
layout: post
title: Get the intersection or union of a set of sets
date: '2010-02-18T08:26:00+01:00'
tags:
- ruby
- intermediate
- beginner
- submission
tumblr_url: http://rubyquicktips.com/post/396232458/get-the-intersection-or-union-of-a-set-of-sets
---
Here is how to get the intersection or union of a set of sets:

a = [[1,2,3],[2,3,4],[3,4,5]]

# get the union:
a.inject(a.first) { |f,x| f = f | x } # => [1, 2, 3, 4, 5]

# get the intersection:
a.inject(a.first) { |f,x| f = f & x } => [3]


Check out these previous tips for more on the individual commands used here:

Inject your enumerables
Set intersection
Set union
This tip was submitted by Alexander Seidl.
