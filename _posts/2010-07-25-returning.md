---
layout: post
title: Returning
date: '2010-07-25T13:00:00+02:00'
tags:
- rubyonrails
- intermediate
tumblr_url: http://rubyquicktips.com/post/856496968/returning
---
schmidt-happens:

Ruby/Rails never ceases to amaze me. Once again while digging around in the source code of Rails I came across Object#returning. Let me introduce you to this little gem.

If you have been writing code for any amount of time then this should look quite familiar to you.

def some_method
  some_var = []
  some_var << ''foo''
  some_var << ''bar''
  return some_var
end


I know, that example was really deep but just bare with me (there is a reason for it’s simplicity). This is a very common workflow when writing code. You initialize an object and assign it to some variable.

some_var = []


Then you perform some über secret work.

some_var << ''foo''
some_var << ''bar''


And finally you return the stuffed object to be used somewhere else. Fortunately, the clever lads behind Rails have enhanced the Object class with a method called ‘returning’. This method takes that workflow and simplifies it. Here is an example of the same workflow above but using Object#returning instead.

def some_method
  returning some_var = [] do
    some_var << ''foo''
    some_var << ''bar''
  end
end


There you have it. Simple. Clean. Elegant. There is an alternative syntax although I personally don’t think it is as intuitive as the one above. But, because I don’t discriminate, here is the more cryptic example.

def some_method
  returning [] do |some_var|
    some_var << ''foo''
    some_var << ''bar''
  end
end


The reason that I feel this style is more cryptic is that it is not immediately clear what you are ‘returning’. At first glance you may be thinking that it is returning an empty array when what it is really returning is the variable ‘some_var’ after the work in the block has been performed. That, of course, is one of the great things about Ruby (and many other languages). You often have several different ways of accomplishing the same goal.
