---
layout: post
title: Testing CSV file uploads
date: '2012-07-22T10:22:54+02:00'
tags:
- rubyonrails
tumblr_url: http://rubyquicktips.com/post/27753730620/testing-csv-file-uploads
---
Let’s say you have a form like this for uploading a CSV file:


  <%= form_tag csv_import_path, :multipart => true do %>
  <%= file_field_tag :file, :accept => "text/csv" %>
  <%= submit_tag "Upload" %>
<% end %>


And your controller action looks like this:


  require ''csv''

def csv_import    
  file_data = params[:file].read
  csv_rows  = CSV.parse(file_data)

  csv_rows.each do |row|
    # do something with each row
  end
    
  respond_to do |format|
    format.html { redirect_to your_path, :notice => "Successfully imported the CSV file." }
  end
end


How would you test this functionality?

You can’t use fixture_file_upload and stick a sample file in test/fixtures/files/ (as often suggested - e.g. here on SO). That’s because CSV and YAML files will be imported as fixtures into the test database as soon as you run tests. E.g., this would not work:


  def test_file_upload
  post :csv_import, :file => fixture_file_upload(''files/new_users.csv'',''text/csv'')
end


But what you can do is to use the Tempfile and Rack::Test::UploadFile classes and manually create a CSV file and supply this to the post (or put) method:


  def test_should_successfully_import_csv
  csv_rows = <<-eos
Name1,name1@example.com
Name2,name2@example.com
Name3,name3@example.com
eos

  file = Tempfile.new(''new_users.csv'')
  file.write(csv_rows)
  file.rewind

  assert_difference "User.count", 3 do
    post :csv_import, :file => Rack::Test::UploadedFile.new(file, ''text/csv'')
  end

  assert_redirected_to your_path
  assert_equal "Successfully imported the CSV file.", flash[:notice]
end
