---
layout: post
title: Update with a touch
date: '2010-01-29T11:59:50+01:00'
tags:
- rubyonrails
- intermediate
tumblr_url: http://rubyquicktips.com/post/359479185/update-with-a-touch
---
From Rails 2.3.3 on, you can update the updated_at time stamp of an instance with touch:

user.updated_at #=> "Wed Jan 27 23:29:22 +1300 2010"
user.touch
user.updated_at #=> "Wed Jan 27 23:30:08 +1300 2010"


You can also update associated parent models by specifying the :touch option on the relation:

class Organization < ActiveRecord::Base
  has_many :users
end

class User < ActiveRecord::Base
  belongs_to :organization, :touch => true
end


Now, whenever you update a user record, the associated organization record will get the updated_at field updated, too.

There is a bit more to it, so check out Ryan Daigle’s blog post and the Rails API.
