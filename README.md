# Symfony 5 Docker Boilerplate
This is a ready to use Docker boilerplate for running Symfony 5 with Docker containers using docker-compose tool.

### Stack
- nginx (`nginx:latest`)
- PHP 8.0 (`php:8.0-fpm`)
- MySQL 8 (`mysql:8`)
- Symfony 5

### How to use
- Clone the repository
- Change `.env` variables if needed
- Run `docker-compose up -d --build` command inside cloned repository

### Hierarchy
- `app` - contains Symfony 5 app files
- `build` - contains Dockerfiles, nginx configuration and PHP configuration
- `db` - contains database data

### How to configure Xdebug with PhpStorm
- Go to `File > Settings... > PHP > Debug`
- In **Xdebug** section change `Debug port` to `9003`
- Go to `File > Settings... > PHP > Servers`
- Add a new server, name it `docker-server`, set `host` to `localhost` and `port` to `8080`
- Check `Use path mappings` and set **Absolute path** to `var/www/symfony/public` next to the `app/public` folder on the left side
- Go to `Add Configuration...` and add new `PHP Remote Debug` configuration
- Check `Filter debug connection by IDE key`, set `server` to our newly created server and set `IDE key` to `PHPSTORM`