---
layout: post
title: 'Benchmark.ms: Rails you sneaky devil.'
date: '2011-01-20T06:23:02+01:00'
tags:
- rubyonrails
tumblr_url: http://rubyquicktips.com/post/2838217166/benchmarkms-rails-you-sneaky-devil
---
I am sure that we have all had to track how long some bit of code takes to process. For auditing purposes or whatever. The typically way we do this is to save the time just before the execution of our action, perform the action, and then get the time when the action completes. End time - Start time = Elapsed time. Hurrah! Look at us being geniuses….

And now for the “bring you back to earth because we did something the not so Rails (or rather Ruby) way” moment. Rails, in it’s sneakiness has extended the Benchmark class and given us a method called #ms. This method receives a block of code and gives the elapsed time for a return result. Did you catch that? Did you really? Because I said the #ms functions return result is the elapsed time. Not the result of the block. This, if you aren’t keeping it in mind can cause a problem.

Thar be Dragons

Let’s say you want to see how long it takes to look up a person in your DB (simple but gets the point across). You might start out by doing something like this:

ms_murder = User.find(:first, :conditions => { :some => "condition" })


Then you think to yourself “I wonder how long that takes”. So you now know about the Benchmark#ms function to you just wrap your previous code like so

Benchmark.ms do
  ms_murder = User.find(:first, :conditions => { :some => "condition" })
end
#=> 0.33299827575684


Great! now you know how long it takes. But wait. What happens when you try to use your ms_murder object?

ms_murder.login
#=> NameError: undefined local variable or method `ms_murder'' for #<Object:0x1001972a0>


Wah wah. The problem here should be obvious but just to clarify the variables that are defined within the Benchmark#ms block are not available outside of that. There are a few ways around this. The first is to initialize the vars before the code block, blech. The second is to use instance variables, warm and fuzzy. I’m sure there are other more creative ways but I have found this works for most of my needs:

Benchmark.ms do
  @ms_murder = User.find(:first, :conditions => { :some => "condition" })
end
#=> 0.33299827575684

@ms_murder.login
#=> "jerrol"


You can also do this if you need to keep the elapsed time around for whatever reason.

elapsed_time = Benchmark.ms do
  @ms_murder = User.find(:first, :conditions => { :some => "condition" })
end
#=> 0.33299827575684

@ms_murder.login
#=> "jerrol"

elapsed_time
#=> 0.33299827575684
