# Create New Rails App

## Steps to create app

### 1.  Create app:

```        
$ rails new AppName -database=postgresql
```

### 2.  Update `app/config/environments/production.rb`. Change from   `false` to `true`:

```
# Do not fallback to assets pipeline if a precompiled asset is missed.
config.assets.compile = true
```

### 3. Update `config/database.yml`:

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

### 4. Create initial database

```
$ rake db:create:all
```

### 5. Set up Git

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
### 6.  Install testing environments
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

### 7. Create controller
Run this command to create controller.
```
$rails generate controller <controller_name>
```

### 8. Create model
```
$rails generate model <modal_names> <col_name>:<col_type>
```

### 9. Add [Bootstrap](Add Twitter Bootstrap 3 to Rails app.md) gem

### 10. Add [Simple_form](https://github.com/plataformatec/simple_form) gem 

### 11. Add [Devise](https://github.com/plataformatec/devise) gem

### 10.  Deploying to Heroku. Create an app name that is unique on heroku.com:

```
$ heroku create New-Unique-App-Name
```

```
$ git push heroku master
```
