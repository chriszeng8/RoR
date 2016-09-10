This request hits the Rails router (Step 2), which dispatches the request to the proper
 controller action based on the URL (and, as we’ll see in Box 3.2, the type of request). 
 The code to create the mapping of user URLs to controller actions for the Users resource 
 appears in Listing 2.5.

```
Rails.application.routes.draw do
  resources :users
  root 'application#hello'
end
```

###REST (REpresentational State Transfer)
REST is an architectural style for developing distributed, networked systems and software applications such as the World Wide Web and web applications.

This index action has the line @users = User.all (Step 3 in Figure 2.11), 
which asks the User model to retrieve a list of all the users from the database (Step 4), 
and then places them in the variable @users (pronounced “at-users”) 
```
  def index
    @users = User.all
  end
```


One of powerful feature of Rails is to form associations between different data models.

A user has many microposts (app/models/user.rb)
```
 class User < ApplicationRecord
  has_many :microposts
end
```
A micropost belongs to a user (app/models/micropost.rb)
```
 class Micropost < ApplicationRecord
  belongs_to :user
  validates :content, length: { maximum: 140 }
end
```
$ rails console
>> first_user = User.first
=> #<User id: 1, name: "Michael Hartl", email: "michael@example.org",
created_at: "2016-05-15 02:01:31", updated_at: "2016-05-15 02:01:31">
>> first_user.microposts
=> [#<Micropost id: 1, content: "First micropost!", user_id: 1, created_at:
"2016-05-15 02:37:37", updated_at: "2016-05-15 02:37:37">, #<Micropost id: 2,
content: "Second micropost", user_id: 1, created_at: "2016-05-15 02:38:54",
updated_at: "2016-05-15 02:38:54">]
>> micropost = first_user.microposts.first    # Micropost.first would also work.
=> #<Micropost id: 1, content: "First micropost!", user_id: 1, created_at:
"2016-05-15 02:37:37", updated_at: "2016-05-15 02:37:37">
>> micropost.user
=> #<User id: 1, name: "Michael Hartl", email: "michael@example.org",
created_at: "2016-05-15 02:01:31", updated_at: "2016-05-15 02:01:31">
>> exit
```


###Inheritance

Model:

we see that both the User model and the Micropost model inherit (via the left angle bracket <) from ApplicationRecord, which in turn inherits from ActiveRecord::Base, 

Controller:
Both the Users controller and the Microposts controller inherit from the Application controller. The ApplicationController itself inherits from ActionController::Base, which is the base class for controllers provided by the Rails library Action Pack.