For detailed instruction:
https://devcenter.heroku.com/articles/git

1. install pg gem (postgres)
Heroku uses the PostgreSQL database, which means that we need to add the pg gem in the production environment to allow Rails to talk to Postgres.

```
group :production do
  gem 'pg',             '0.17.1'
  gem 'rails_12factor', '0.0.2'
end
```

The whole Gemfile:
```
source 'https://rubygems.org'

gem 'rails', '4.2.0'
gem 'sass-rails', '5.0.1'
gem 'uglifier', '2.5.3'
gem 'coffee-rails', '4.1.0'
gem 'jquery-rails', '4.0.3'
gem 'turbolinks', '2.3.0'
gem 'jbuilder', '2.2.3'
gem 'sdoc', '0.4.0' , group: :doc

group :development, :test do
  gem 'sqlite3',     '1.3.9'
  gem 'byebug',      '3.4.0'
  gem 'web-console', '2.0.0.beta3'
  gem 'spring',      '1.1.3'
end

group :production do
  gem 'pg',             '0.17.1'
  gem 'rails_12factor', '0.0.2'
end
```




```
Uploading /Users/apple1/.ssh/id_rsa.pub SSH key... done
ApplematoMacBook-Pro:hello_app apple1$ heroku create
Creating app... done, ⬢ desolate-shelf-57146
https://desolate-shelf-57146.herokuapp.com/ | https://git.heroku.com/desolate-shelf-57146.git
```