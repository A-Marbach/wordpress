# WordPress Docker Project

## Table of Contents
- [Description](#description)
- [Quickstart](#quickstart)
- [Usage](#usage)
- [Extras](#extras)

## Description
This repository contains a Docker Compose setup for running WordPress with a MySQL database.  
The project is designed to be easy to deploy, with persistent data storage and configurable environment variables.

### Key Features
- WordPress latest version in Docker
- MySQL 8 database
- Persistent volumes for WordPress files and database
- Easy configuration via environment variables
- Automatic container restart on failure

---

## Quickstart

### Prerequisites
- Docker
- Docker Compose
- (Optional) VSCode or another code editor

### Steps
1. Clone this repository:

```bash
git clone <https://github.com/A-Marbach/minecraft-server>
cd wordpress
```
2. Create a .env file (optional, for custom credentials):

```
WORDPRESS_DB_NAME=mywordpress
WORDPRESS_DB_USER=admin
WORDPRESS_DB_PASSWORD=geheim123
MYSQL_ROOT_PASSWORD=rootpass
```
3. Start the containers:
```bash
docker-compose up -d
```

4. Open Wordpress in your browser:
```
http://localhost:8080
```

## Usage

### Environment Variables

You can modify .env or the environment section in docker-compose.yaml:

| Variable | Description | Default |
|----------|-------------|---------|
| WORDPRESS_DB_NAME | Database name for WordPress | wordpress |
| WORDPRESS_DB_USER | WordPress DB user | user |
| WORDPRESS_DB_PASSWORD | Password for WordPress DB user | password |
| MYSQL_ROOT_PASSWORD | Root password for MySQL | rootpassword |

### Volumes

wordpress_data: stores WordPress files (themes, plugins, uploads)

db_data: stores MySQL database files

Volumes ensure data persists even after container restarts or recreation.

Restarting Containers

```bash
dokcer-compose restart
```

Stopping Containers

```bash
dokcer-compose down
```

### Extras

You can install additional WordPress plugins by adding them to wp-content/plugins/

Custom themes can be added in wp-content/themes/

For debugging, view logs:

```bash
docker-compose logs wordpress
docker-compose logs db
```

### Notes

Do not commit .env to the repository; it contains sensitive information.

Ensure Docker and Docker Compose are installed on your machine or VM before starting.