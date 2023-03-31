# Installation
```bash
# build
docker-compose run --no-deps web rails new . --force --database=postgresql

# owner
ll
sudo chown -R $USER:$USER .

# rebuild because of gemfile initialized
docker-compose build

# edit config/database.yml
# ---------------------------------------
default: &default
  adapter: postgresql
  encoding: unicode
  host: db
  username: postgres
  # docker-compose define
  password: password
  pool: 5

development:
  <<: *default
  database: myapp_development


test:
  <<: *default
  database: myapp_test
# ---------------------------------------

# start app & db
docker-compose up

# create db
docker-compose run web rake db:create

# check access
# http://localhost:3000

# stop app & db
docker-compose down



# after edit files
docker-compose up --build
docker-compose run web bundle install
```

# Ref
https://matsuand.github.io/docs.docker.jp.onthefly/samples/rails/