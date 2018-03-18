---
layout: post
title: 'Spell: Dynamic Dispatch'
date: '2010-11-29T20:00:06+01:00'
tags:
- ruby
- intermediate
- submission
tumblr_url: http://rubyquicktips.com/post/1728928971/spell-dynamic-dispatch
---
Coming from java - from time to time it just has to be… “copy-paste-time”. You’re used to it:

puts "response.inspect: #{response.inspect}"
puts "response.error_type: #{response.error_type}"
puts "response.response: #{response.response}"
puts "response.body: #{response.body}"


But wait - this is Ruby! Let’s have some fun with that spell I read about: Dynamic Dispatching. Let’s define a method that takes the object and the method to be called:

def show_response_method(method_to_call, response)
  puts "response.#{method_to_call}: #{response.send(method_to_call)}"
end


Now, we don’t have to repeat the textual output all the time:

show_response_method :inspect, response
show_response_method :error_type, response
show_response_method :response, response
show_response_method :body, response


And, in a more Ruby-like manner, we can bum some lines by using this little fellow:

[:inspect, :error_type, :response, :body].each { |method| show_response_method method, response }


We could furthermore use the Open Class concept and get funky with a little Monkey Patching and inject this method into the response object itself - but this would be one of the cases where monkey patching is not the right thing to do. At least, this is my opinion. What do you think about it?

This tip was submitted by 5v3n.
