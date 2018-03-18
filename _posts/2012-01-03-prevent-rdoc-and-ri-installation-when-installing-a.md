---
layout: post
title: Prevent rdoc and ri installation when installing a gem
date: '2012-01-03T06:00:06+01:00'
tags:
- ruby
- rubyonrails
- submission
tumblr_url: http://rubyquicktips.com/post/15226105447/prevent-rdoc-and-ri-installation-when-installing-a
---
When installing a gem the process that often takes the longest is generating the ri and RDoc documentation.

If you want to prevent this from happening every time a gem gets installed (either manually or through Bundler), create (or open) a .gemrc file in ~/.gemrc or /etc/gemrc and add the following two lines:


  install: --no-ri --no-rdoc
update: --no-ri --no-rdoc


(If you want to overwrite this default per gem, or if you want to install the documentation later, you can do so by passing --ri and/or --rdoc options to the gem install command.)

The .gemrc file is the configuration file used by RubyGems, in which you can specify command-line arguments to be used every time the gem command runs: more about the RubyGems configuration file.

This tip was submitted by Andrea Singh.
