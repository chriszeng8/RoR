
1. install Rails with specific version number
```
$ gem install rails -v 4.2.0
```


2. Run Rails new (with a specific version number _#.#.#_)
```
￼$ cd ~/workspace
$ rails _4.2.0_ new hello_app
```
Note: running ```rails new``` automatically runs the ```bundle install``` command after the file creation is done.


3. We can make some changes to the default application gems and run Bundler again. This involves opening the Gemfile with a text editor. (With the cloud IDE, this involves clicking the arrow in the file navigator to open the sample app directory and double-clicking the Gemfile icon.)

Example:

```
￼gem 'coffee-rails', '~> 4.0.0
```

where ```~>``` represents getting the latest version within minor changes (third digital in version number is changed)
This installs the gem coffee-rails as long as it’s newer than version 4.0.0 and not newer than 4.1.

example of explicitly specified Gemfile:
```
source 'https://rubygems.org'
gem 'rails', '4.2.0'
gem 'sass-rails', '5.0.1'
gem 'uglifier', '2.5.3'
gem 'coffee-rails', '4.1.0'
gem 'jquery-rails', '4.0.3'
gem 'turbolinks', '2.3.0'
gem 'jbuilder', '2.2.3'
gem 'sdoc', '0.4.0', group: :doc
group :development, :test do
  gem 'sqlite3',     '1.3.9'
  gem 'byebug',      '3.4.0'
  gem 'web-console', '2.0.0.beta3'
￼  gem 'spring',      '1.1.3'
end
```

4. Once the `Gemfile` is modified, execute ```bundle install```.
```
￼$ cd hello_app/
$ bundle install
``` 

5. Run a local web server.
```
$ rails server
```
