
# Exercício 1 microserviços


## Inicializar projeto

```sh
mvn sprint-boot:run
```

### Gerar container

```sh
./mvnw install dockerfile:build
```

### Rodar container

```sh
docker run -p 8000:8000 -t springio/payment-service
```


## Pagamentos

#### Listar

```sh
curl -X GET \
  http://localhost:8080/payments \
  -H 'content-type: application/json'
```

#### Inserir

```sh
curl -X POST \
  http://localhost:8080/payments \
  -H 'cache-control: no-cache' \
  -H 'content-type: application/json' \
  -H 'postman-token: 7d70adc0-5275-b464-fb35-efae9e7a917f' \
  -d '{
    "brand": "MASTERCARD",
    "transactionType": "CREDIT",
    "cardNumber": "5277 2155 0199 7257",
    "expDate": "03/20",
    "cvv": 493,
    "price": 20.00
}'
```

#### Carregar

```sh
curl -X GET \
  http://localhost:8080/payments/6fd6a1d7-277a-a149-b7bc-e9e6ecdf02f9 \
  -H 'content-type: application/json'
```

#### Alterar

```sh
curl -X PUT \
  http://localhost:8080/payments \
  -H 'cache-control: no-cache' \
  -H 'content-type: application/json' \
  -H 'postman-token: 7d70adc0-5275-b464-fb35-efae9e7a917f' \
  -d '{
    "brand": "MASTERCARD",
    "transactionType": "CREDIT",
    "cardNumber": "5277 2155 0199 7257",
    "expDate": "03/20",
    "cvv": 493,
    "price": 20.00
}'
```

#### Remover

```sh
curl -X DELETE \
  http://localhost:8080/payments/6fd6a1d7-277a-a149-b7bc-e9e6ecdf02f9
```

