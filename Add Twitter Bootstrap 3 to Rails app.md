Add Twitter Bootstrap 3 to Rails app

source:	http://www.thefirehoseproject.com/nomster/7

1.	add to Gemfile:
	gem ‘bootstrap-sass’, ‘~3.3.51’
	gem 'sprockets', '2.11.0'
	gem ‘sass-rails’ #(comment out sass-rails’,’~>4.0.0’
	(bundle install,restart rails server)

2.	‘mv app/assets/stylesheets/application.css app/assets/stylesheets/application.scss’

3. 	add 	‘@import "bootstrap-sprockets";
			 @import “bootstrap";'
		to 'application.scss'

4.	add	'//=require bootstrap-sprockets' as 2nd line in app/assets/javascripts/application.js

