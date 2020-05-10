```console
docker-compose run --rm --no-deps web rails new . -fT -d postgresql --force
docker-compose run --rm --no-deps solargraph
docker-compose build
sudo chown -R $USER:$USER ./app
```

config/database.yml￼

```yaml
default: &default
  adapter: postgresql
  encoding: unicode
  host: db
  username: postgres
  password:
  pool: <%= ENV.fetch("RAILS_MAX_THREADS") { 5 } %>
```

```console
docker-compose run --rm web rails db:create
$ docker-compose up
```
