# Go Event Handler

Este projeto em Go é composto por duas aplicações. Uma que publica a mensagem "Hello World!" em uma exchange do RabbitMQ e outra que a consome e a imprime no terminal.

## Requisitos

- Go 1.21
- Docker
- Docker Compose
- No RabbitMQ:
  1. Acessar através do endereço `http://localhost:15672` com as credenciais `guest:guest`
  2. Criar uma **Queue** chamada `my-queue`
  3. Criar uma **Exchange** chamada `amq.direct`
  4. Criar um **Binding** entre a Queue `my-queue` e a Exchange `amq.direct`

## Funcionalidades

O produtor publica a mensagem no RabbitMQ e o consumidor a consome e a imprime no terminal.

1. **Publicação de mensagem no RabbitMQ:**
- A aplicação publica a mensagem `"Hello World!"` na exchange  `amq.direct` do RabbitMQ.

2. **Consumo de mensagem no RabbitMQ:**
- A aplicação consome a mensagem publicada na exchange `amq.direct` do RabbitMQ e a imprime no terminal.

## Execução do Aplicativo

**Execute o RabbitMQ:**
```bash
docker-compose up -d
```

**Execute o consumidor:**
```bash
go run cmd/consumer/main.go 
```

**Abra um novo terminal e execute o produtor:**
```bash
go run cmd/producer/main.go 
```

**Nota:** No terminal do consumidor, a mensagem `"Hello World!"` será impressa.
