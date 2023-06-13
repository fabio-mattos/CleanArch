## Desafio 03 - Go Expert - Clean Architecture 

Coloquei a mão na massa para fixar o aprendizado da aquitetura limpa.
Neste desafio, criei a listagem das orders.

Listagem feita com:

- Endpoint REST (GET /order)
- Service ListOrders com GRPC
- Query ListOrders GraphQL


## Como Testar

1) Com o git clonar o repositporio 

2) Subir o banco de dados com docker:

  Na pasta home do projeto, matar tudo do docker e subir o docker-compose.

    docker rm -f
    
    docker-compose up -d

2) Entrar no mysql para criar o banco e tabela

    docker-compose exec mysql bash

    mysql -uroot -p orders
    password: root

    CREATE TABLE orders (id varchar(255) NOT NULL, price float NOT NULL, tax float NOT NULL, final_price float NOT NULL, PRIMARY KEY (id));


3) Subir a aplicação.
    Entrar na pasta ordersystem
     -> cd cmd/ordersystem
  
       go run main.go wire_gen.go


### Endpoints REST

- `POST localhost:8000/order` - endpoint para gerar uma novo pedido.
- `GET localhost:8000/list_orders` - endpont para listar todas as ordens.

### GraphQL

- `localhost:8080`

###  gRPC

- `CreateOrder` - criar um novo pedido
- `ListOrders` - listar pedidos

### Acesso RabbitMQ
 
endpoint: http://localhost:15672

usuário: guest
senha: guest

 