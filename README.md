# MySQL Docker Container Setup

Este documento fornece instruções sobre como executar o container MySQL, acessar o banco de dados e restaurar dados.

## Pré-requisitos

- Docker e Docker Compose instalados no seu sistema.
- Arquivo `.env` configurado com as variáveis de ambiente necessárias.

## Configuração do Arquivo .env

O arquivo `.env` deve conter as seguintes variáveis de ambiente:

```plaintext
MYSQL_ROOT_PASSWORD=mysql@123
MYSQL_USER=mysql
MYSQL_PASSWORD=mysql@123
MYSQL_DATABASE=DATA
MYSQL_BACKUP=backup
```

## Executando o Container

1. Navegue até o diretório onde o arquivo `docker-compose.yml` está localizado.

2. Execute o seguinte comando para iniciar o container em segundo plano:

   ```bash
   docker-compose up -d