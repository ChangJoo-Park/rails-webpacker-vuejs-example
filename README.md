# README

## Using Ruby on Rails with vue.js

### Create Project

```
rails new {app-name} --webpack=vue
```

### Create App / Index page in Home Controller

```
rails g controller Home index app
```

### Add Vue App in App page

**app.html.erb**

```
<%= javascript_pack_tag 'hello_vue' %>
```

### Using webpack-dev-server with foreman

```
# ./Procfile
web: bundle exec puma -p $PORT

# ./Procfile.dev
web: bundle exec rails s
# watcher: ./bin/webpack-watcher
hot: ./bin/webpack-dev-server

# ./bin/server

#!/bin/bash -i
bundle install
bundle exec foreman start -f Procfile.dev

# chmod 777 ./bin/server

# Gemfile
group :development do
  gem 'foreman'
end
```

### Add webpacker dev_server_hot to development.rb
```
config.x.webpacker[:dev_server_host] = "http://localhost:8080"
```

run `./bin/server` and open url `http://localhost:5000`
