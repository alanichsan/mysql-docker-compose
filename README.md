# MySQL Docker Compose

This repository contains a simple setup for running a MySQL database using Docker Compose. It allows you to quickly deploy a MySQL instance for development and testing purposes.

## Table of Contents

- [Prerequisites](#prerequisites)
- [Getting Started](#getting-started)
- [Configuration](#configuration)
- [Accessing MySQL](#accessing-mysql)

## Prerequisites

Make sure you have Docker and Docker Compose installed on your machine. You can download and install them from the following links:
- [Docker](https://www.docker.com/get-started)
- [Docker Compose](https://docs.docker.com/compose/install/)

## Getting Started

1. **Clone the repository**:
   ```sh
   git clone https://github.com/alanichsan/mysql-docker-compose.git
   cd mysql-docker-compose
2. **Start the MySQL service:**:
   ```sh
   docker-compose up -d
3. **Stopping the MySQL service:**:
   ```sh
   docker-compose down
## Configuration
The configuration for the MySQL service is defined in the `docker-compose.yml` file. By default, the configuration is set to:

```
version: '3.1'

services:
  db:
    image: mysql:latest
    restart: always
    environment:
      MYSQL_ROOT_PASSWORD: rootpassword
      MYSQL_DATABASE: exampledb
      MYSQL_USER: exampleuser
      MYSQL_PASSWORD: examplepass
    ports:
      - "3306:3306"
    volumes:
      - db_data:/var/lib/mysql

volumes:
  db_data:
```
You can customize the environment variables (`MYSQL_ROOT_PASSWORD`, `MYSQL_DATABASE`, `MYSQL_USER`, and `MYSQL_PASSWORD`) according to your needs.


## Accessing MySQL
You can access the MySQL database from the command line using the following command:
```
docker exec -it mysql-docker-compose_db_1 mysql -uexampleuser -pexamplepass exampledb
```
Replace mysql-docker-compose_db_1 with the actual container name if it's different.

