---
layout: post
title: Find your hidden puts statement when testing
date: '2010-07-19T11:27:33+02:00'
tags:
- beginner
- rubyonrails
- intermediate
- submission
tumblr_url: http://rubyquicktips.com/post/831412465/find-your-hidden-puts-statement-when-testing
---
When trying to track down an issue in rspec or cucumber I often use puts to quickly read the value of a variable. Sometimes, though, I forget to take the statement out and have a hard time locating the file and line number. To quickly find out exactly where the puts statement is (or any other call you are having a hard time tracking down), just open up your environment.rb file and add this:

def puts(value)
  raise ''you found a puts''
end

Now run your tests again and the overridden method will throw an error giving you a stack trace with the file and line number. Just don’t forget to remove the code before you push to production. ;)

This tip was submitted by Chris Young.
