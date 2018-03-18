---
layout: post
title: Step through your Cucumber features one step at a time
date: '2011-08-26T08:04:06+02:00'
tags:
- rubyonrails
- submission
tumblr_url: http://rubyquicktips.com/post/9407081385/step-through-your-cucumber-features-one-step-at-a
---
If you want to step through your cucumber scenarios simulating an interactive debugger, add this hook:


  AfterStep(''@pause'') do
  print "Press Return to continue..."
  STDIN.getc
end


Then tag any feature with “@pause” and you’re all set.
