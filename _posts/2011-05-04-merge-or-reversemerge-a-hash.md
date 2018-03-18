---
layout: post
title: Merge or reverse_merge a Hash
date: '2011-05-04T12:46:10+02:00'
tags:
- ruby
- rubyonrails
tumblr_url: http://rubyquicktips.com/post/5186906190/merge-or-reversemerge-a-hash
---
Ruby’s Hash#merge lets you merge two Hashes. Duplicate entries in the merged Hash taking precedence over then ones in the calling Hash:


  h1 = { "a" => 100, "b" => 200 }
h2 = { "b" => 254, "c" => 300 }
h1.merge(h2)   #=> {"a"=>100, "b"=>254, "c"=>300}
h1             #=> {"a"=>100, "b"=>200}


Rails’ Hash#reverse_merge takes the opposite approach when it comes to handle duplicate entries. The API docs perfectly describe what it’s good for, giving an example of a very common practise regarding a method’s options:


  Allows for reverse merging two hashes where the keys in the calling hash take precedence over those in the other_hash. This is particularly useful for initializing an option hash with default values:



  def setup(options = {})
  options.reverse_merge! :size => 25, :velocity => 10
end



  Using merge, the above example would look as follows:



  def setup(options = {})
  { :size => 25, :velocity => 10 }.merge(options)
end



  The default :size and :velocity are only set if the options hash passed in doesn’t already have the respective key.


Both methods are also available in their Bang versions merge! and reverse_merge!.

Here are the docs: Hash#merge (Ruby) and Hash#reverse_merge (Rails).

All code examples taken from the respective API docs.
