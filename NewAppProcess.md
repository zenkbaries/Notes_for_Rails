# Create New Rails App

## Steps to create app

### 1.  Create app:

```        
$ rails new AppName --database=postgresql
```
### 2. Add this Gem `rails_12factor` for production group. It's needed if you plan to host on Heroku.
As group:
```ruby
group :production do
  # Use for to prevent Heroku to inject plug-in
  # https://devcenter.heroku.com/articles/ruby-support#injected-plugins
  gem 'rails_12factor'
end
```
or as one liner:
```ruby
# Use for to prevent Heroku to inject plug-in
# https://devcenter.heroku.com/articles/ruby-support#injected-plugins
gem 'rails_12factor', group: :production
```


### 3.  Update `/config/environments/production.rb`. Change from   `false` to `true`:

```
# Do not fallback to assets pipeline if a precompiled asset is missed.
config.assets.compile = true
```

### 4. Update `config/database.yml`:

```ruby
development:
adapter: postgresql
encoding: unicode
database: splurty_development
pool: 5
username: postgres
password: password
host: localhost

test:
adapter: postgresql
encoding: unicode
database: splurty_test
pool: 5
username: postgres
password: password
host: localhost


production:
adapter: postgresql
encoding: unicode
database: splurty_production
pool: 5
username: postgres
password: password
host: localhost
```

### 5. Create initial database

```
$ rake db:create:all
```

### 6. Set up Git

```
$ git init .
```

```
$ git add --all
```

```
$ git commit -am "Inital Commit"
```

```

$ git remote add origin git@github.com:zenkbaries/<repositery_name_here>.git

```

```
$ git push -u origin master
```
### 7.  Install testing environments
Add these line at the bottom of `Gemfile`

```ruby
group :development, :test do
  gem 'rspec-rails', '~> 3.0'
end
```
Run this commands:
```
$bundle install
$rails generate rspec:install
```
Remove test folder:
```
$rm -rf test
```

Run the test
```
$bundle exec rspec
```

### 8. Create controller
Run this command to create controller.
```
$rails generate controller <controller_name>
```

### 9. Create model
```
$rails generate model <modal_names> <col_name>:<col_type>
```

### 10. Add [Bootstrap](Add Twitter Bootstrap 3 to Rails app.md) gem

### 11. Add [Simple_form](https://github.com/plataformatec/simple_form) gem

```
 Be sure to have a copy of the Bootstrap stylesheet available on your
  application, you can get it on http://getbootstrap.com/.

  Inside your views, use the 'simple_form_for' with one of the Bootstrap form
  classes, '.form-horizontal' or '.form-inline', as the following:

    = simple_form_for(@user, html: { class: 'form-horizontal' }) do |form|
```

### 12. Add [Devise](https://github.com/plataformatec/devise) gem

### 13. Make sure gemfile has this at the top of the file.

```ruby
source "https://rubygems.org"
ruby "2.2.3" #put in your current Ruby version you are using
```

for more info:https://devcenter.heroku.com/articles/ruby-versions


### 14.  Deploying to Heroku. Create an app name that is unique on heroku.com:

```
$ heroku create New-Unique-App-Name
```

```
$ git push heroku master
```
