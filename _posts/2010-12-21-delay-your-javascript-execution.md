---
layout: post
title: Delay your Javascript execution
date: '2010-12-21T04:57:58+01:00'
tags:
- rubyonrails
tumblr_url: http://rubyquicktips.com/post/2396960828/delay-your-javascript-execution
---
There’s a Prototype helper method called delay, so you can more precisely say when something will happen.
For example, you can do stuff like this inside your RJS files:

page["old_element"].visual_effect :blind_up, :duration => 0.5

page.delay(0.5) do
  page.replace :old_element, :partial => "new_element"
  page["new_element"].visual_effect :blind_down
end


Check out the delay method.
