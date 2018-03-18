---
layout: post
title: FIXME, TODO and OPTIMIZE code comments
date: '2010-02-12T17:20:52+01:00'
tags:
- rubyonrails
- intermediate
tumblr_url: http://rubyquicktips.com/post/385665023/fixme-todo-and-optimize-code-comments
---
You can add some special notes to your source code comments in Rails to remind you later of stuff you need to do:

class Article < ActiveRecord::Base
  # TODO add named_scopes
  # FIXME method A is broken
  # OPTIMIZE improve the code 

  has_many :comments
  ....
end


You can list these special notes with a rake task:

$ rake notes
app/models/article.rb:
  * [2] [TODO] add named_scopes
  * [3] [FIXME] method A is broken
  * [4] [OPTIMIZE] improve the code


You can also list notes of each kind individually with rake notes:todo, rake notes:fixme and rake notes:optimize.
You can even list your own, custom notes with rake notes:custom ANNOTATION=MYANNO.
