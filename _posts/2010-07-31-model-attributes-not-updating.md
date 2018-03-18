---
layout: post
title: Model attributes not updating? reset_column_information to the rescue!
date: '2010-07-31T13:00:00+02:00'
tags:
- rubyonrails
- intermediate
tumblr_url: http://rubyquicktips.com/post/883943520/model-attributes-not-updating
---
So you were wondering why some of your model attributes weren’t updating properly? Well, it is perhaps because the db schema has changed but the changed schema has not been passed onto ActiveRecord, as is often the case in DB migration.

Taken from the ActiveRecord documentation:


  Resets all the cached information about columns, which will cause them to be reloaded on the next request.
  
  The most common usage pattern for this method is probably in a migration, when just after creating a table you want to populate it with some default values, eg:


class CreateJobLevels < ActiveRecord::Migration
  def self.up
    create_table :job_levels do |t|
      t.integer :id
      t.string :name

      t.timestamps
    end

    JobLevel.reset_column_information
    %w{assistant executive manager director}.each do |type|
      JobLevel.create(:name => type)
    end
  end

  def self.down
    drop_table :job_levels
  end
end
