---
layout: post
title: Returning 'false' in a callback will halt execution
date: '2010-02-13T17:25:55+01:00'
tags:
- rubyonrails
- intermediate
tumblr_url: http://rubyquicktips.com/post/387377542/returning-false-in-a-callback-will-halt
---
When you return false from a callback method, the whole execution chain will be halted.

Since Ruby implicitly returns the result of the last expression of a method, this can cause unexpected problems. The following example shows such a case:

class Article < ActiveRecord::Base
  before_update :close_comments, :if => :more_than_ten_comments
  ...
  protected

  def close_comments
    # this will cause the execution chain to halt,
    # but you probably didn''t intend to do so
    self.open_for_comments = false
  end
end


In this case, the save method will return false and the save! method will throw an RecordNotSaved error.

So: always keep this in mind when you code your callbacks.
