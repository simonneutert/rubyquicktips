---
layout: post
title: Disabling input fields on a form based on a condition
date: '2010-01-14T23:18:50+01:00'
tags:
- beginner
- intermediate
- rubyonrails
tumblr_url: http://rubyquicktips.com/post/334692052/disabling-input-fields-on-a-form-based-on-a
---
You may know about the :disabled option for form elements such as buttons, text-fields etc:

submit_tag "Pay", :disabled => true


Did you know, you can pass any boolean expression as a value?

submit_tag "Pay", :disabled => @cart.empty?


(via Using conditions in Form Helpers of Rails)
