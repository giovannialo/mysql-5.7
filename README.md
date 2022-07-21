# MySQL v5.7

Banco de dados MySQL v5.7 para Docker.

## Dependências

* Repositório [Nginx Proxy + Let's Encrypt](https://github.com/giovannialo/nginx-proxy-letsencrypt).

#### Observação

É necessário realizar os procedimentos de instalação do repositório acima antes de iniciar o processo de instalação abaixo.

## Instalação

Siga as etapas abaixo para um correto funcionamento do sistema.

### Variáveis de ambiente

Faça uma cópia do arquivo **.env.example** para **.env** e configure as variáveis conforme a sua necessidade.

#### Exemplo

```dotenv
MYSQL_USER=user
MYSQL_PASSWORD=user
MYSQL_ROOT_PASSWORD=root
MYSQL_TIMEZONE=America/Maceio
MYSQL_CHARSET=utf8mb4
MYSQL_COLLATION=utf8mb4_unicode_ci
```

### Permissões básicas do usuário simples (não root)

Abra o arquivo **set-grant-permission-to-user.sql** e, onde tem a palavra **user**, altere para o mesmo valor de **MYSQL_USER** do arquivo **.env**.

```sql
TRIGGER ON *.* TO 'user'@'%';
```

### Container

Execute o comando abaixo para criar e iniciar o container.

```docker
docker-compose up -d
```

## Credits

* [Giovanni Alves de Lima Oliveira](https://github.com/giovannialo) (Developer)
