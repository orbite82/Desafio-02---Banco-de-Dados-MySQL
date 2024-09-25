<div align="center">
<img src="https://user-images.githubusercontent.com/47891196/139104117-aa9c2943-37da-4534-a584-e4e5ff5bf69a.png" width="350px" />
</div>

# Desafio 02 - Banco de Dados MySQL

Para criar um container MySQL com os requisitos que você mencionou, você pode usar o seguinte comando Docker:

```bash
docker run --name mysql_container -e MYSQL_ROOT_PASSWORD=root_pwd -e MYSQL_DATABASE=docker_db -e MYSQL_USER=docker_usr -e MYSQL_PASSWORD=docker_pwd -p 3306:3306 -d mysql:latest
```

### Explicação dos parâmetros:

- `--name mysql_container`: Nomeia o container como `mysql_container`.
- `-e MYSQL_ROOT_PASSWORD=root_pwd`: Define a senha do usuário root do MySQL.
- `-e MYSQL_DATABASE=docker_db`: Cria o banco de dados `docker_db`.
- `-e MYSQL_USER=docker_usr`: Cria um usuário chamado `docker_usr`.
- `-e MYSQL_PASSWORD=docker_pwd`: Define a senha do usuário `docker_usr`.
- `-p 3306:3306`: Mapeia a porta 3306 do container para a porta 3306 do host.
- `-d mysql:latest`: Executa o container em segundo plano usando a imagem mais recente do MySQL.

```bash
docker run --name my_mysql_container \
-e MYSQL_ROOT_PASSWORD=docker_pwd \
-e MYSQL_DATABASE=docker_db \
-e MYSQL_USER=docker_usr \
-e MYSQL_PASSWORD=docker_pwd \
-d -p 3306:3306 mysql:latest
```
# Ou

- `-d`: Executa o container em segundo plano.
- `mysql:latest`: Usa a imagem mais recente do MySQL.

### Acessando o Banco de Dados

Para acessar o banco de dados usando o novo usuário:

```bash
docker exec -it my_mysql_container mysql -u docker_usr -p
```

Quando solicitado, insira a senha `docker_pwd`.
