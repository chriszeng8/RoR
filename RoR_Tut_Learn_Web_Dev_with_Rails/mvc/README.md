Standard Rails application structure has a directory:
```app/``` with three subdirectories: ```models```, ```views```, and ```controllers```.

MVC: enforces separation between "business logic"

```model (data model)```: data such as users, articles, products

```controller```: when browser send a request, it is received by a web server and passed onto a (Rails) controller, 
the controller decides what to do next, and then render a view.
More commonly for dynamic sites, the controller interacts with a model, which is a Ruby object that represents an element of the site (such as a user) and is in charge of communicating with the database. 
After invoking the model, the controller then renders the view and returns the complete web page to the browser as HTML.

```view```: a template that gets converted to HTML and sent back to the browser


###Create a Controller
* Make a wafer-thin change to the default app by adding a controller action to render a 'hello world' text.

1. Controller actions are defined in controllers. Let's create our own controller.
2. Add a hello action into application_controller.rb
```
class ApplicationController < ActionController::Base
  # Prevent CSRF attacks by raising an exception.
  # For APIs, you may want to use :null_session instead.
  protect_from_forgery with: :exception
  
  def hello
    render text: "hello world"
  end
end
```
3. Edit the router (config/routes.rb) to use the added action: 

we need to tell Rails to use that action instead of the default page
To do this, we’ll edit the Rails router, which sits in front of the controller in Figure 1.11 and determines where to send requests that come in from the browser.
The root URL is often re- ferred to as / (“slash”) for short.

```
Rails.application.routes.draw do
  .
  .
  .
  # You can have the root of your site routed with "root" 
  #follow the format $ root 'controller_name#controller_action'
  root 'welcome#index'
end
```
Here “welcome” is the controller name and “index” is the action within that controller. To activate the root route

In our case, we need:
```
Rails.application.routes.draw do
  .
  .
  .
  # You can have the root of your site routed with "root" 
  root 'application#hello'
  .
  .
  .
end
```

It should be noted that the controller file name, and class name should follow the convention:

* controller ruby file:

file name in lower case separate followed by '_controller.rb': 
    controllername_controller.rb 

classname in Camel Case:
    class ControllernameController < ActionController::Base

* controller name reference:
    controller#action
    
