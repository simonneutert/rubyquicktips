---
layout: post
title: Mark Deprecated Code in Ruby
date: '2012-03-27T11:32:46+02:00'
tags:
- ruby
- submission
tumblr_url: http://rubyquicktips.com/post/20002932888/mark-deprecated-code-in-ruby
---
To mark deprecated code in Ruby simply add a comment to the rdoc and call the Kernel#warn method.  For example:


  class Foo
  # DEPRECATED: Please use useful instead.
  def useless
    warn "[DEPRECATION] `useless` is deprecated.  Please use `useful` instead."
    useful
  end

  def useful
    # ...
  end
end


If you’re using Yard instead of rdoc, your doc comment should look like this:


  # @deprecated Please use {#useful} instead


Also, don’t forget to remove the deprecated method in some future release.

Source: Ryan McGeary’s answer on stackoverflow.
