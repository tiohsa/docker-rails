```console
$ docker-compose run --rm --no-deps web rails new . -fT -d postgresql --force
$ sudo chown -R $USER:$USER ./rails_app
$ docker-compose build
```

config/database.yml￼

```yaml
default: &default
  adapter: postgresql
  encoding: unicode
  host: db
  username: postgres
  password: postgres
  pool: <%= ENV.fetch("RAILS_MAX_THREADS") { 5 } %>
```

```console
$ docker-compose run --rm web rails db:create
$ docker-compose up
```

vscode solargraph extension

```json
  "solargraph.transport": "external",
  "solargraph.externalServer": {
    "host": "localhost",
    "port": 8091
  },
  "docker-linter.rubocop.machine": "docker-rails_web_1"
```
