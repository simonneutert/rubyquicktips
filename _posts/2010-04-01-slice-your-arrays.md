---
layout: post
title: Slice your Arrays
date: '2010-04-01T12:00:00+02:00'
tags:
- ruby
- intermediate
- submission
tumblr_url: http://rubyquicktips.com/post/488750875/slice-your-arrays
---
To get every pair of consecutive elements of an array use the Enumerable#each_cons method:

[0,1,2,3,4,5].each_cons(2).to_a # => [[0, 1], [1, 2], [2, 3], [3, 4], [4, 5]]


The sister method is Enumerable#each_slice which partitions the array into arrays of the specified size:

[0,1,2,3,4,5].each_slice(2).to_a # => [[0, 1], [2, 3], [4, 5]]


Both each_cons and each_slice can f.e. be used with Array#shuffle to obtain random subgroups of an array:

[0,1,2,3,4,5].shuffle.each_slice(3).to_a #=> [[1, 4, 0], [3, 2, 5]]


Please note, that the methods each_cons and each_slice belong to the Enumerable class and are therefor also available to other object types - such as Hashes f.e. - that include the Enumerable module. The shuffle method is a method of the Array class and can only be called on Arrays.

This tip was submitted by Erik Andrejko.
