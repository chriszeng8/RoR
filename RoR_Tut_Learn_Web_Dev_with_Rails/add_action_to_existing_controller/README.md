Here we are showing how to add a new action called ```about``` to ```StaticPages``` controller. Basically, there are 3 elements needed to added:

* router (add URL here)
* controller (add action definition here)
* html view (add div within html)

1. **Router**: add a GET request for URL ```static_pages/about``` which is routed to ```about``` action in ```StaticPages``` controller. (note that the url is in snake_case, and the controller class names are in CamelCase).

```
Rails.application.routes.draw do
  get  'static_pages/home'
  get  'static_pages/help'
  get  'static_pages/about'
  root 'application#hello'
end
```

2. **Controller.rb**: add def for ```about``` action.

```
class StaticPagesController < ApplicationController

  def home
  end

  def help
  end

  # New action defined here
  def about
  end
end
```

3. **HTML**: add ```app/views/static_pages/about.html.erb``` which follows the format ```app/views/controller_name/action.html```.
