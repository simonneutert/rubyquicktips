---
layout: post
title: String#gsub with a block generates the substitution string dynamically
date: '2012-01-19T06:00:05+01:00'
tags:
- ruby
- submission
tumblr_url: http://rubyquicktips.com/post/16102760378/stringgsub-with-a-block-generates-the
---
String#gsub is a common method for finding and replacing all occurrences of a text in a string. It is often used, like this:


  "Where is the needle in the haystack?".gsub(''needle'', ''NEEDLE'')
# => "Where is the NEEDLE in the haystack?"


But gsub can also use regular expressions, like this:


  "Where is the needle in the haystack?".gsub(/n\w{5,}/, ''*'')
# => "Where is the * in the haystack?"


gsub can also take a block which can use all of the global match variables, such as $&, $'', $1, $2, to build up a replacement string. This allows for replacement strings to be generated using information from the match, like this:


  "Where is the needle in the nefarious haystack?".gsub(/n\w{5,}/) do
  ''*'' + $&.upcase + ''*''
end
# => "Where is the *NEEDLE* in the *NEFARIOUS* haystack?"


Blocks provide gsub with the ability to generate the substitution string using information about a match that is only available after a match is identified. You can use any of the global variables associated with matches from within the block.

This tip was submitted by Tim Rand.
