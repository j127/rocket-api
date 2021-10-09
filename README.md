# README

Based on [this](https://genekuo.medium.com/creating-a-rest-api-in-rust-with-persistence-rust-rocket-and-diesel-a4117d400104).

## Database

```text
$ docker container run \
    --rm \
    --name pg-tmp \
    --env POSTGRES_USER=username \
    --env POSTGRES_PASSWORD=password \
    -p 5432:5432 \
    postgres:13-alpine
```

## Migrations

Install the diesel CLI:

```text
$ cargo install diesel_cli --no-default-features --features "postgres"
```

Setup:

```text
$ diesel setup
```

Create a migration:

```text
$ diesel migration generate create_posts
```

Add your SQL to the two generated files, and then create the schema file like this:

```text
$ diesel migration run
```
