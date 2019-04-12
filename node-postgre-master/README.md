API nodejs + postgre + Oauth2

Criando o banco:

psql postgres
postgres=# CREATE ROLE me WITH LOGIN PASSWORD 'password';
postgres=# ALTER ROLE me CREATEDB;
postgres=# \q
psql -d postgres -U me
postgres=> CREATE DATABASE api;
postgres=> \c api
api=>
CREATE TABLE users (
  ID SERIAL PRIMARY KEY,
  name VARCHAR(30),
  email VARCHAR(30)
);
INSERT INTO users (name, email)
  VALUES ('Jerry', 'jerry@example.com'), ('George', 'george@example.com');


Para rodar, executar:

node index.js

Pegar lista de usuários:
curl http://localhost:3000/users

Pegar usuário com id igual a x
curl http://localhost:3000/users/x

Cadastrar usuário:
curl -X POST -d "name=Ian" -d "email=ian@example.com" http://localhost:3000/users

Update em usuário:
curl -X PUT -d "name=Kramer" -d "email=kramer@example.com" http://localhost:3000/users/1

Deletar usuários de id igual a x:
curl -X DELETE http://localhost:3000/users/x
"# ServidorOAuth-Postgresql" 
