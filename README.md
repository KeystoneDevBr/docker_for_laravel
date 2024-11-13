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

## Acessando o container da Aplicação e do Banco de Dados
```
# Aplicação
https://localhost


# PhpMyadmin
https://localhost:4443
```


### Observações
#### Para correta instalação do Container do SQS Server, siga as instruções contindas em;
 
[./docker/developer/sqlsrv/README.md](.docker/developer/sqlsrv/README.md)

ou 

[./docker/production/sqlsrv/README.md](.docker/production/sqlsrv/README.md)



#### Para compartilhar na internet o projeto utilizando o Ngrok siga os passo abaixo

##### Passo 1: Instalar e configurar o Agnete [Ngrok](https://ngrok.com)
```
#INSTALAR O NGROK

brew install ngrok/ngrok/ngrok

#CONFIGURAR O TOKEN
ngrok config add-authtoken <SEU-TOKEN>
```
##### Passo 2: Expor o projeto localhost via Ngrok

Como o conteiner docker está configurado para redirecionar as conexões http para https, 
o serivço exposto deverá ser  o https apenas

```

ngrok http --host-header=rewrite localhost:443

#0u

ngrok http --host-header=rewrite localhost:443

#Com google

ngrok http  localhost:443 --oauth=google --oauth-allow-domain="mycorp.com"

```

##### Passo 3: Acessar o site pela url gerada no comando anterior

[https://bcee-2804-d59-8927-d000-a052-671a-bf45-b7b5.ngrok-free.app](https://dashboard.ngrok.com/endpoints)