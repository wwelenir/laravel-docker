# laravel-docker-base
Environment created to facilitate the development of Laravel applications using Docker.

### Specifications:
- Laravel 7 
- PHP 7.4 
- MySQL 5.7 
- PHPMyAdmin 5.1.1
- NGINX

## Configuring environment:
- Fork the project to your github
- Make a clone to your local machine
- Access the src folder and via terminal execute the commands:
 ```
  cp .env.example .env
 ```
 ```
  php artisan key:generate
```
- Open the .env file and make the following settings:
  ```
  DB_HOST=mysql
  DB_DATABASE=laravel
  DB_USERNAME=username
  DB_PASSWORD=password
  ```
  - Go back to the project root folder and run the following command to start docker:
 ```
  docker-compose up -d
 ```
 - With the container created, open the browser and test access to Laravel localhost:8080 e PHPMyAdmin: localhost:8081
 - Now the next step is executing the migrations, we will access our application inside the container with the following command:
```
docker exec -it laravel-docker-base-php-fpm-1 /bin/bash
```
- Inside the application folder, run the following commands to give permission to the storage folder and generate the application migrations:
```
chmod -R 777 storage/
```
```
php artisan migrate
```


 
