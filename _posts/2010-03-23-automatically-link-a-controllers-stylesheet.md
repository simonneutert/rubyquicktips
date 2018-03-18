---
layout: post
title: Automatically link a controller's stylesheet
date: '2010-03-23T18:00:00+01:00'
tags:
- rubyonrails
- intermediate
tumblr_url: http://rubyquicktips.com/post/468246164/automatically-link-a-controllers-stylesheet
---
This is a simple application helper that shaunchapman wrote to reduce the tediousness of linking stylesheets for each controller. It will link the controller’s stylesheet (located at public/stylesheets/[controller_name].css) if it exists but it won’t complain if it doesn’t. It is a nice way to keep things organized and it’s super simple to set up.

Simply add this to your application helper (located at app/helpers/application_helper.rb):

def controller_stylesheet_link_tag
  stylesheet = "#{params[:controller]}.css"
    
  if File.exists?(File.join(Rails.public_path, ''stylesheets'', stylesheet))
    stylesheet_link_tag stylesheet
  end
end

…and put this in your application layout (located at app/views/layouts/application.html.erb):

<%= controller_stylesheet_link_tag %>
