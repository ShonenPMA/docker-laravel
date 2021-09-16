# DOCKER LARAVEL PHPMYADMIN MYSQL NGINX

Use WordPress locally with Docker using [Docker compose](https://docs.docker.com/compose/)

## Instructions

<details>
 <summary>Requirements</summary>

+ [Docker](https://www.docker.com/get-started)

</details>

<details>
 <summary>Setup</summary>

 ### Setup Environment variables

#### 1. For Docker and Wordress (Required step)

Copy `.env.example` in the project root to `.env` and edit your preferences.

Example:

```dotenv
MYSQL_ROOT_PASSWORD=root
MYSQL_DATABASE=homestead
MYSQL_USER=homestead
MYSQL_PASSWORD=secret

PHPMYADMIN_PORT=8090
NGINX_PORT= 8092

OS_USER=ubuntuUser # to get your current user, run: whoami
OS_UID=1000
```
</details>

<details>
<summary>Run</summary>

# Run docker-compose

```shell
docker-compose up -d
```
## Laravel

🚀 Open [http://localhost:8092](http://localhost:8092) in your browser

## PhpMyAdmin

PhpMyAdmin comes installed as a service in docker-compose.

🚀 Open [http://localhost:8090/](http://localhost:8090/) in your browser

</details>
<details>
<summary>Using bin directory</summary>

# Copy files

1. Copy ./config/bin files  in /usr/local/bin path
2. (In VScode) Go to your workspace settings and add the follow config in json file

```json
    "php.validate.executablePath" :  "/usr/local/bin/phplaravel"
```

3. Check in your root project path running the commands

```shell
phplaravel --version
```
Output:

```shell
Running php on docker test_php_1
PHP 7.4.23 (cli) (built: Sep  3 2021 17:58:14) ( NTS )
Copyright (c) The PHP Group
Zend Engine v3.4.0, Copyright (c) Zend Technologies
```

```shell
composerlaravel --version
```
Output:

```shell
Running composer on docker test_php_1
Composer version 2.1.5 2021-07-23 10:35:47
```

</details>
<details>
<summary>Creating a new Laravel project</summary>

# Using the bin files

## Run the command
```shell
composerlaravel create-project laravel/laravel .
```
## Config the env file to connect with database using the mysql container, for example
```dotenv
DB_CONNECTION=mysql
DB_HOST=mysql
DB_PORT=3306
DB_DATABASE=homestead
DB_USERNAME=homestead
DB_PASSWORD=secret
```

</details>