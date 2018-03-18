---
layout: post
title: Associations with Conditions
date: '2011-09-12T12:53:07+02:00'
tags:
- rubyonrails
tumblr_url: http://rubyquicktips.com/post/10122386367/associations-with-conditions
---
You can specify ActiveRecord Associations with a condition on them:


  class Post
  has_many :comments
  has_many :published_comments,
           :class_name => "Comment",
           :conditions => { :published => true }
end


One possible use-case is that you can use these associations to eager load only a subset of the associated records:


  post = Post.find(1, :include => :published_comments)
# SELECT "posts".* FROM "posts" WHERE "posts"."id" = ? LIMIT 1  [["id", 1]]
# SELECT "comments".* FROM "comments" WHERE "comments"."post_id" IN (1) AND ("comments"."published" = ''t'')


Read more about this in the API docs about ActiveRecord::Associations.
