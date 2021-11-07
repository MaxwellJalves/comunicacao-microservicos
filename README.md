# comunicacao-microservicos


-   [x] Criar uma instancia do PostgresSQL
-   [x] Criar uma instancia do MongoDB


Criando imagem docker

##Container db-auth
docker run --name db-auth -p 5432:5432 -e POSTGRES_DB:autenticacao -e POSTGRES_USER:adm -e POSTGRES_PASSWORD:123456  postgres:latest

##Container db-produtos 
docker run --name db-produtos -p 5433:5433 -e POSTGRES_DB:db-produtos -e POSTGRES_USER:adm  -e POSTGRES_PASSWORD:123456  postgres:latest


##Container db-vendas  api:node
docker run --name db-vendas  -p 27017:27017 -p 28017:28017 -e MONGODB_DATABASE="db-vendas" -e MONGODB_USER="admin" -e MONGODB_PASS="123456" tutum/mongodb

-- instalar o mongoDb Shell

https://www.mongodb.com/try/download/shell

-   metodos
https://docs.mongodb.com/mongodb-shell/reference/methods/


String de conexão para acesso ao banco  "mongodb://admin:123456@localhost:27017/db-vendas"
script :


mongosh "mongodb://admin:123456@localhost:27017/db-vendas"

-   criando collection / tabela
    db.vendas  

-   inserindo dados
    db.vendas.insert({"codigo": 1, "descricao": "itens teste"})

-   Buscando registros
    db.vendas.find()
