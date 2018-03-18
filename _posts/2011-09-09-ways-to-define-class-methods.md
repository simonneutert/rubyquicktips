---
layout: post
title: Ways to define class methods
date: '2011-09-09T08:50:23+02:00'
tags:
- ruby
tumblr_url: http://rubyquicktips.com/post/9988400756/ways-to-define-class-methods
---
There are different ways to create class methods in Ruby. These three are probably the most common ones. They all do the same.


  class Blog

  def self.foo
    puts ''I am a class method''
  end

  def Blog.bar
    puts ''I am a class method, too''
  end

  class << self
    def foobar
      puts ''I am another class method''
    end
  end

end


There are even more ways to define class methods. Check out these two post for more:

Ruby: Defining Class Methods
Class and Instance Methods in Ruby
