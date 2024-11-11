# Containers Docker para Integração de Projetos com Laravel ou PHP

### Versão: 1.0.0

### Containers Disponíveis para Ambiente Dev e Production:

```
Ngix:1.27.0
PHP:8.3-fpm
PhpMyAdmin
PgAdmin4
Mysql
MariaDb
PostgreSQL
SQL Server:2022-latest
```

### Como instalar o docker lado a lado com o seu projeto Laravel.
```
# Passo 1: Copie o projeto para dentro da raiz do projeto Laravel.

git clone https://github.com/KeystoneDevBr/docker_for_laravel.git

# Copiar o conteúdo da parta docker_for_laravel para dentro da raiz do projeto do laravel
# (Obs) o arquivo .env do diretório destino será sobrescrito

mv ./docker_for_laravel/* . ~/path/meuProjetoLaravel

# Execulte o script docker-compose.sh para istalar as instâncias do docker

cd ~/path/meuProjetoLaravel

./docker-compose.sh --build

# Prosseguir com a instalação do projeto laravel no container do Php

docker ps
docker -exec -it <id-do-container-php> bash
composer install
        .
        .
        .
php artisan up

```


### Observações
#### Para correta instalação do Container do SQS Server, siga as instruções contindas em;
 
[./docker/developer/sqlsrv/README.md](./docker/developer/sqlsrv/README.md)

ou 

[./docker/production/sqlsrv/README.md](.docker/production/sqlsrv/README.md)

