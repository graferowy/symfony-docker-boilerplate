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