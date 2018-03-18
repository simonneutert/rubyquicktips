---
layout: post
title: I'll put the "squeeze" on ya
date: '2010-04-19T13:00:00+02:00'
tags:
- ruby
- intermediate
- beginner
tumblr_url: http://rubyquicktips.com/post/533010887/ill-put-the-squeeze-on-ya
---
Have you ever been in a situation where you have duplicated characters in a string and wanted to blast them like you were playing Jerry Bruckheimer? Well I recently ran into a situation where I wanted to take a string and change all the non-word characters to and underscore.

string = "The Title: A Best Seller by Unknown"
string.gsub(/\W/, ''_'')
#=> "The_Title__A_Best_Seller_by_Unknown"


Hrm, almost what I want but the only problem is those extra underscores. I thought surely there has to be a way to easily get rid of them. I mean surely! That’s when I dove into the String class and discovered the String#squeeze method. Here’s what the documentation says:


  Builds a set of characters from the other_str parameter(s) using the procedure described for String#count. Returns a new string where runs of the same character that occur in this set are replaced by a single character. If no arguments are given, all runs of identical characters are replaced by a single character.


Basically what this is saying is that this method will look for any characters that repeat and replace them with only a single occurrence of that character. By default it will look for any character that appears more than once consecutively. Enough chit chat, time for examples!

# Vanilla call
"Tweet Me the message".squeeze
#=> "Twet me the mesage"

# With a specific character specified
"yellow moon".squeeze(''o'')
#=> "yellow mon"

# You can even pass it a range of characters to look for. From the documentation
"putters shoot balls".squeeze("m-z")
#=> "puters shot balls"


This is exactly what I want. Now I just have to adjust my original code and this is what I get:

string = "The Title: A Best Seller by Unknown"
string.gsub(/\W/, ''_'').squeeze(''_'')
#=> "The_Title_A_Best_Seller_by_Unknown"


This tip was reblogged from schmidt-happens.
