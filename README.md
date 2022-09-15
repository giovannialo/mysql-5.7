# MySQL v5.7

Banco de dados MySQL v5.7 para Docker.

## Dependências

* Docker Compose;
* Rede venus.

## Instalação

Siga as etapas abaixo para um correto funcionamento do sistema.

### Rede venus

Para efetivar uma comunicação entre os serviços, é preciso que todos os containers estejam utilizando a mesma rede.
Execute o comando abaixo para criar a rede venus.

```docker
docker network create --driver bridge venus
```

### Variáveis de ambiente

Na pasta raiz crie um arquivo chamado .env, copie e cole o bloco de código abaixo e configure as variáveis.

```dotenv
MYSQL_USER=usuario
MYSQL_PASSWORD=senha
MYSQL_ROOT_PASSWORD=root
MYSQL_TIMEZONE=America/Maceio
MYSQL_CHARSET=utf8mb4
MYSQL_COLLATION=utf8mb4_unicode_ci
```

### Permissões do usuário não root

Abra o arquivo **set-grant-permission-to-basic-user.sql** e, onde tem a palavra **usuario**, altere para o mesmo valor
de **MYSQL_USER** do arquivo **.env**.

```sql
TRIGGER
ON *.* TO 'usuario'@'%';
```

### Container

Execute o comando abaixo para criar e iniciar o container.

```docker
docker-compose up -d
```

## Credits

* [Giovanni Alves de Lima Oliveira](https://github.com/giovannialo) (Developer)
