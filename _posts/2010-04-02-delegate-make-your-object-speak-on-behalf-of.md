---
layout: post
title: 'Delegate: Make your object speak on behalf of another object'
date: '2010-04-02T19:00:00+02:00'
tags:
- rubyonrails
- intermediate
- submission
tumblr_url: http://rubyquicktips.com/post/491561623/delegate-make-your-object-speak-on-behalf-of
---
Say you have a one-to-many relationship between two models and you need to use this relationship to do some calculations.
For example, we have a OrderLine model that uses the price method of the associated Product model to calculate the sub total for the OrderLine.

Here is the example:

class Product < ActiveRecord::Base
  has_many :order_lines
end

class OrderLine < ActiveRecord::Base
  belongs_to :order
  belongs_to :product

  def sub_total
    quantity * product.price
  end

  def to_s
    # 5 Bikes, unit price 2.0, total 10.0
    "#{quantity} #{product.descripton},
     unit price #{product.price}, total #{sub_total}"
  end
end


In the above code we have to specify the product object when we want to get the price in the sub_total method.
Would it not be nicer to just be able to say quantity * price in the sub_total method (without product. in front)? It would certainly be clearer in explaining the intent.
So, let us make our OrderLine speak for our product when we call the price method. Delegate, baby!

class OrderLine < ActiveRecord::Base
  belongs_to :order
  belongs_to :product

  delegate [:descripton, :price], :to => :product

  def sub_total
    quantity * price
  end

  def to_s
    # 5 Bikes, unit price 2.0, total 10.0
    "#{quantity} #{descripton},
     unit price #{price}, total #{sub_total}"
  end
end


We can use the delegate class method to specify that the OrderLine model should delegate calls to description and price to the Product model.
Isn’t this cool?

This tip was submitted by Marcus Wyatt.
