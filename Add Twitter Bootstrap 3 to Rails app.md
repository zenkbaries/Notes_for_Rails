# Add Twitter Bootstrap 3 to Rails app
github:https://github.com/twbs/bootstrap-sass

source:	http://www.thefirehoseproject.com/nomster/7

## 1.	Add to Gemfile:
```ruby
gem ‘bootstrap-sass’, ‘~3.3.51’
gem 'sprockets', '2.11.0'
```

Add the following if it's not already listed.
```ruby
gem ‘sass-rails’ #comment out sass-rails’,’~>4.0.0’
```

Run this command:
```
$bundle install
```
If you have error from `bundle install` related to 	`sprockets` run this command to update the gem.
```
$bundle update sprockets
```
Restart rails server
```
$rails server
```

## 2. Import Bootstrap styles in `app/assets/stylesheets/application.scss`:

```scss
// "bootstrap-sprockets" must be imported before "bootstrap" and "bootstrap/variables"
@import "bootstrap-sprockets";
@import "bootstrap";
```
## 3.	Rename  `application.css`.
Rename `application.css` to `application.scss` in `app/assets/stylesheets` directory

```
$cd app/assets/stylesheets
$mv application.css application.scss
$cd ../../../
```



## 4.	Modify `app/assets/javascripts/application.js` to look like this:

```javascripts
//= require jquery
//= require bootstrap-sprockets
//= require jquery_ujs
//= require turbolinks
//= require_tree .
```

## 5. Done
