# laravel-docker-base
Ambiente criado para facilitar o desenvolvimento de aplicações Laravel utilizando docker.

### Especificações:
- Laravel 7 
- PHP 7.4 
- MySQL 5.7 
- PHPMyAdmin 5.1.1
- NGINX

## Configurando ambiente:
- Efetue um fork do projeto para seu github
- faça um clone para sua maquina local
- Rcesse a pasta src e via terminal execute os comando:
 ```
  cp .env.example .env
 ```
 ```
  php artisan key:generate
```
- Abra o arquivo .env e efetue a seguinte configurações:
  ```
  DB_HOST=mysql
  DB_DATABASE=laravel
  DB_USERNAME=username
  DB_PASSWORD=password
  ```
  - Volte para a pasta raiz do projeto e execute o seguinte comando para iniciar o docker:
 ```
  docker-compose up -d
 ```
 - Com o container criado abra o navegador e teste os acessos ao Laravel: localhost:8080 e PHPMyAdmin: localhost:8081
 - Agora o proximo passo e a execução dos migrations, vamos acessar nossa aplicação dentro do container com o seguinte comando:
```
docker exec -it laravel-docker-base-php-fpm-1 /bin/bash
```
- Dentro da pasta aplication execute os seguintes comandos para dar permissao a pasta storage e gerar os migrations da aplicação:
```
chmod -R 777 storage/
```
```
php artisan migrate
```


 
