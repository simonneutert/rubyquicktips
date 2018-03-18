---
layout: post
title: Some Array magic using transpose, map and reduce
date: '2012-03-06T11:06:41+01:00'
tags:
- ruby
- submission
tumblr_url: http://rubyquicktips.com/post/18842314838/some-array-magic-using-transpose-map-and-reduce
---
To add on corresponding elements of several arrays:


  a = [1, 2, 3]
b = [4, 5, 6]
c = [7, 8, 9]

[a, b, c].transpose.map { |x| x.reduce :+ }
# => [12, 15, 18]


Given a number of arrays, each contains same number of arrays with the same length. To merge corresponding arrays:


  a = [ [1, 2], [3, 4] ]
b = [ [5, 6], [7, 8] ]
c = [ [9, 10], [11, 12] ]

(a.transpose + b.transpose + c.transpose).transpose
# => [[1, 2, 5, 6, 9, 10], [3, 4, 7, 8, 11, 12]]


To do the same job, but with arrays that are not necessarily equal in length:


  a = [ [1], [2, 3] ]
b = [ [4, 5], [] ]
c = [ [6,7,8], [9, 10, 11, 12] ]

[a, b, c].transpose.map { |x| x.reduce :+ }
# => [[1, 4, 5, 6, 7, 8], [2, 3, 9, 10, 11, 12]]


Check out the documentation on Array#transpose, Array#map and Enumerable#reduce.

This tip was submitted by Haitham Mohammad.
