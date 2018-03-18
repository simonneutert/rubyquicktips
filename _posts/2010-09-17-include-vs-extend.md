---
layout: post
title: Include vs. Extend
date: '2010-09-17T00:00:00+02:00'
tags:
- ruby
- intermediate
tumblr_url: http://rubyquicktips.com/post/1133877859/include-vs-extend
---
You can either use include or extend to mix in a module’s functionality into a class. The difference is this:

include makes the module’s methods available to the instance of a class, while
extend makes these methods available to the class itself.
Check out this example:

module Greetings
  def say_hello
    puts "Hello!"
  end
end

class Human
  include Greetings
end

Human.new.say_hello # => "Hello!"
Human.say_hello     # NoMethodError

class Robot
  extend Greetings
end

Robot.new.say_hello # NoMethodError
Robot.say_hello     # => "Hello!"


If you want more information on include vs. extend, I recommend the following resources:

What is the difference between include and extend in Ruby? on Stack Overflow.
Include vs Extend in Ruby by John Nunemaker
Ruby extend and include by Jay Fields
