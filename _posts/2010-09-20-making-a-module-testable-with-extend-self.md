---
layout: post
title: Making a module testable with 'extend self'
date: '2010-09-20T00:12:22+02:00'
tags:
- ruby
- intermediate
- submission
tumblr_url: http://rubyquicktips.com/post/1152365215/making-a-module-testable-with-extend-self
---
It’s great to pull out common functionality into a module, so you can use it in several classes. But it can be a little awkward to test the module, because you can’t call its methods directly.
Well, unless you can: use extend self to make the module’s instance methods available as class methods. Now you can call the methods of the module directly without having an instance of a class that includes this module.

module ShoutMachine
  extend self

  def shout(text)
    "#{text.upcase}!"
  end
end

class BigMachine
  include ShoutMachine
end

>> ShoutMachine.shout(''booyeah'')   # => BOOYEAH!
>> BigMachine.new.shout(''booyeah'') # => BOOYEAH!


This tip was submitted by Nick Stielau.
