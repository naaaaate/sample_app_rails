# Ruby on Rails Tutorial: sample application

Generated new rails app from scratch.
Created new controller w actions:
 rails g controller static_pages home help

Defined new routes in config/routes.rb
  routes defined as:  get 'controllerName / action'
  root route defined as: root 'controllerName#action'

Created about page html.erb file view.
added to each view the erb code: <% provide (:title, "Home"/"Help"/"About") %>

Edited application.html.erb layout file
  this file incorporated <%= yield (:title) %> to insert the :title var from the provide method on each page..

Incorporated Tests:
  for controllers:
  creating controller will create the controller test
  used methods:
    test 'text it should do'  do
      get :about  - get the about page.
      assert_response :success  - return a success that it exists.
      assert_select "title", "text it should contain" - for html elements
    end


# add minitest reporters and use it to add green and red to our tests
require "minitest/reporters"
Minitest::Reporters.use!


# adding a backtrace silencer to remove unnecessary code in errors.
Rails.backtrace_cleaner.add_silencer { |line| line =~ /rvm/ }

# add guard to automate running of tests.
$ bundle exec guard init

guard :minitest, spring: true, all_on_start: false do
  guard uses Spring server to speed up loading times. and prevents guard from running full tests on start

add to guard to git ignore file
# Ignore Spring files.
/spring/*.pid


#add helper method for title.. so that blank titles have def value..
  module ApplicationHelper

  # Returns the full title on a per-page basis.
  def full_title(page_title = '')
    base_title = "Ruby on Rails Tutorial Sample App"
    if page_title.empty?
      base_title
    else
      page_title + " | " + base_title
    end
  end
end

--then add the helper method to the application page..
<title><%= full_title(yield(:title)) %> </title>
















This is the sample application for the
[*Ruby on Rails Tutorial:
Learn Web Development with Rails*](http://www.railstutorial.org/)
by [Michael Hartl](http://www.michaelhartl.com/).