---
layout: post
title: Initialize Objects with a Hash
date: '2012-02-07T06:00:06+01:00'
tags:
- ruby
- submission
tumblr_url: http://rubyquicktips.com/post/17196977143/initialize-objects-with-a-hash
---
If you want to initialize new instances of your class and specify values for its attributes directly, you can implement an initialize method with a lot of arguments. Or you can use a Hash - the Rails way:


  my_puppy = Dog.new(:name => "Luke", :birthdate => Time.now)


You can do this by using a general initialize implementation:


  module GeneralInit
  def initialize(*h)
    if h.length == 1 && h.first.kind_of?(Hash)
      h.first.each { |k,v| send("#{k}=",v) }
    end
  end
end


For every class that needs to take advantage of this, you just have to include GeneralInit. The initialize method will be available and work the way you expect it to.
It is still possible to create a new instance without arguments (Dog.new), or passing in a Hash with attribute/value pairs (as shown in the example above).

This tip was submitted by Rik Vanmechelen.
