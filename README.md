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




This is the sample application for the
[*Ruby on Rails Tutorial:
Learn Web Development with Rails*](http://www.railstutorial.org/)
by [Michael Hartl](http://www.michaelhartl.com/).