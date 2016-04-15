# Create New Rails App

## Steps to create app

### 1.	Create app:

```				
$ rails new AppName -database=postgresql
```

### 2.	Update `app/config/environments/production.rb`. Change from 	`false` to `true`:

```
# Do not fallback to assets pipeline if a precompiled asset is missed.
config.assets.compile = true
```

### 3. update `config/database.yml`:

```
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
### 6.	Install testing environments
Add following to `Gemfile`

```
group :development, :test do
gem 'rspec-rails', '~> 3.0'
end
```

###7.	Deploying to Heroku. Create an app name that is unique on heroku.com:

```
$ heroku create New-Unique-App-Name
```

```
$ git push heroku master
```
