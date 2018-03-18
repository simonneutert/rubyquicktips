---
layout: post
title: Rails' include_root_in_json
date: '2012-02-23T06:00:05+01:00'
tags:
- rubyonrails
tumblr_url: http://rubyquicktips.com/post/18115841886/rails-includerootinjson
---
When rendering JSON from your controllers (or when using to_json directly), Rails 3.1 and above won’t include the root element in the output:


  post = Post.first
# => #<Post id: 1, title: "My first blogpost" ...

post.to_json
# => "{\"id\":1,\"title\":\"My first blogpost\", ...}"


To include the root element (post in this example), set ActiveRecord::Base.include_root_in_json to true:


  # wrap_paramters.rb
if defined?(ActiveRecord)
  ActiveRecord::Base.include_root_in_json = true
end


Result:


  post.to_json
# => "{\"post\":{\"id\":1,\"title\":\"My first blogpost\", ...}}"


In version of Rails < 3.1, including the root element is the default. You can disable it by adding ActiveRecord::Base.include_root_in_json = false to one of your files in config/initializers or in application.rb/environment.rb directly.

More info in the API docs on ActiveModel::Serializers::JSON.
