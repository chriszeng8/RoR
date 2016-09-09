###creat toy_app
```
$ cd ~/workspace
$ rails _5.0.0.1_ new toy_app
$ cd toy_app/
```

###Gemfile
```
source 'https://rubygems.org'

gem 'rails',        '5.0.0.1'
gem 'puma',         '3.4.0'
gem 'sass-rails',   '5.0.6'
gem 'uglifier',     '3.0.0'
gem 'coffee-rails', '4.2.1'
gem 'jquery-rails', '4.1.1'
gem 'turbolinks',   '5.0.1'
gem 'jbuilder',     '2.4.1'

group :development, :test do
  gem 'sqlite3', '1.3.11'
  gem 'byebug',  '9.0.0', platform: :mri
end

group :development do
  gem 'web-console',           '3.1.1'
  gem 'listen',                '3.0.8'
  gem 'spring',                '1.7.2'
  gem 'spring-watcher-listen', '2.0.0'
end

group :production do
  gem 'pg', '0.18.4'
end

# Windows does not include zoneinfo files, so bundle the tzinfo-data gem
gem 'tzinfo-data', platforms: [:mingw, :mswin, :x64_mingw, :jruby]
```

###Bundle install while suppressing the installation of production gems 
we’ll install the local gems while suppressing the installation of production gems using the --without production option:

```
$ bundle install --without production
```

*Note*: Just in case that ```rails server``` gives errors, you may need to run ```bundle update``` as well (Box 1.1).
