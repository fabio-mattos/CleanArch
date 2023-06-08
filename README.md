## CleanArch com Golang
Coloquei a mão na massa para fixar o aprendizado da aquitetura limpa.
Neste desafio, criei a listagem das orders.

Listagem feita com:

- Endpoint REST (GET /order)

- Service ListOrders com GRPC

- Query ListOrders GraphQL


## Como Testar

1) Subir o banco de dados

No home do projeto, matar tudo do docker e subir o docker-compose.

    docker rm -f
    
    docker-compose up -d

2) Entrar no mysql para criar o banco e tabela

    docker-compose exec mysql bash

    mysql -uroot -p orders

    CREATE TABLE orders (id varchar(255) NOT NULL, price float NOT NULL, tax float NOT NULL, final_price float NOT NULL, PRIMARY KEY (id));




3) Subir a aplicação.
    Entrar na pasta ordersystem.
     cd cmd/ordersystem
  
    go run main.go wire_gen.go


4) Testar via HTTP

Abrir o arquivo 
 api/create_order.http


5)  Testar via GRPC 
Novo terminal
evans -r repl
call CreateOrder


6) Testar via GraphQL 
localhost:8080
