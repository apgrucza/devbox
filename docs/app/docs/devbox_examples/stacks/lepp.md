---
title: LEPP (Linux, Nginx, PHP, Postgres)
---


An example Devbox shell for NGINX, Postgres, and PHP. This example uses Devbox Plugins for all 3 packages to simplify configuration

[Example Repo](https://github.com/jetpack-io/devbox/tree/main/examples/stacks/lepp-stack)

[![Open In Devbox.sh](https://jetpack.io/img/devbox/open-in-devbox.svg)](https://devbox.sh/new?template=lepp-stack)

## How to Run

### Initializing

In this directory, run:

`devbox shell`

This will run `initdb` automatically on initialization. To start the Servers + Postgres service, run:

`devbox services start`

### Creating the DB

You can run the creation script using `devbox run create_db`. This will create a Postgres DB based on `setup_postgres_db.sql`.

### Testing the Example

You can query Nginx on port 80, which will route to the PHP example.

## How to Recreate this Example

1. Create a new project with `devbox init`
1. Add the packages using the command below. Installing the packages with `devbox add` will ensure that the plugins are activated:

```bash
devbox add postgres php81 php81Extensions.pgsql nginx
```

1. Update `devbox.d/nginx/httpd.conf` to point to the directory with your PHP files. You'll need to update the `root` directive to point to your project folder
2. Follow the instructions above in the How to Run section to initialize your project.
