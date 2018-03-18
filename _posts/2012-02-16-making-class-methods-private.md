---
layout: post
title: Making class methods private
date: '2012-02-16T06:00:00+01:00'
tags:
- ruby
- submission
tumblr_url: http://rubyquicktips.com/post/17698867568/making-class-methods-private
---
This does not work:


  class Foo
  private
  
  def self.bar
  end
end


Foo.bar will be public.
To make it private, you can use Module#private_class_method:


  class Foo
  def self.bar
  end

  private_class_method :bar
end


…or define it differently:


  class Foo
  class << self
    private
        
    def bar
    end
  end
end


This tip was submitted by two-bit-fool.
