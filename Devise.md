# Installing Devise, user authentication gem
## Devise gem

Github:https://github.com/plataformatec/devise

### 1.  Add `devise` gem to gemfile:
```ruby
# use Devise user authentication 
# Only use version 4.0 or forward
gem 'devise', '>= 4.0.0'
```

### 2.  Run bundle install:
```
$ bundle install
```


#### After `bundle install`, the resulting text will show this:

```
===============================================================================

Some setup you must do manually if you haven't yet:

1. Ensure you have defined default url options in your environments files. Here
is an example of default_url_options appropriate for a development environment
in config/environments/development.rb:

config.action_mailer.default_url_options = { host: 'localhost', port: 3000 }

In production, :host should be set to the actual host of your application.

2. Ensure you have defined root_url to *something* in your config/routes.rb.
For example:

root to: "home#index"

3. Ensure you have flash messages in app/views/layouts/application.html.erb.
For example:

<p class="notice"><%= notice %></p>
<p class="alert"><%= alert %></p>

4. If you are deploying on Heroku with Rails 3.2 only, you may want to set:

config.assets.initialize_on_precompile = false

On config/application.rb forcing your application to not access the DB
or load models when precompiling your assets.

5. You can copy Devise views (for customization) to your app by running:

rails g devise:views

===============================================================================
```

### 3. Modify `config/environments/development.rb` to define development default url.
```
config.action_mailer.default_url_options = { host: 'localhost', port: 3000 }
```


### 4. Modify `config/environments/production` to define production url.
```
config.action_mailer.default_url_options = { host: '<yourwebURL.com>' }
```

### 5.	Make sure `config/routes.rb` has root_url pointing to somwhere:

```
root 'notes#index'   #<-- just an example
```

###	6. Ensure you have flash messages in app/views/layouts/application.html.erb.
#### For example:

standard version:
```html
<p class="notice"><%= notice %></p>
<p class="alert"><%= alert %></p>
```

Bootstrap version with conditional statements added:
```html
<% if notice.present? %>
	<p class="alert alert-info"><%= notice %></p>
<% end %>
<% if alert.present? %>
	<p class="alert alert-danger"><%= alert %></p>
<% end %>
```

###	7.	Run this
```
$ rails g devise:views
```

### 8.  Generate User model
It create a user model for user authentication. Run this command.


```
$ rails generate devise User
$ rake db:migrate
```

