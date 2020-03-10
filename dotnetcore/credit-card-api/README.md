# API de Cartão de Crédito

 ## Introdução
 Uma startup está com planos de lançar seu  sistema de cartões, para isso, ela entrou em  contato com você para desenvolver um sistema MVP que permita:
 - Cadastrar um novo cliente
 - Criar um novo cartão
 - Ativar um novo cartão
 - Fazer uma compra em um cartão
 - Consultar a fatura de um cartão
 
 Obs: Por ser apenas um MVP, esse sistema não irá  a público então não há necessidade de um  sistema  de autenticação

 ## Regras de negocio:
 - Não deve ser possivel fazer uma compra em um cartão que não existe
 - Não deve ser possivel criar um cartão de um cliente que não exite
 - Não deve ser possivel fazer uma compra em um cartão que não está active

___
 ## Requisições de Cliente:

 ### POST /client
Cria um cliente no sistema.

**Request Body**
```json
{
    "name": "Obi-Wan Kenobi"
}
```

**Response 201**
```json
{
    "id": 1,
    "name": "Obi-Wan Kenobi"
}
```

 ### GET /client/{id}
Exibe um cliente do sistema

**Response 200**
```json
{
    "id": 1,
    "name": "Obi-Wan Kenobi"
}
```

 ## Requisições de cartão:

 ### POST /card
Cria um cartão no sistema.

**Request Body**
```json
{
    "number": "012730871",
    "clientId": 1
}
```

**Response 201**
```json
{
    "id": 1,
    "number": "012730871",
    "clientId": 1,
    "active": false
}
```

 ### PATCH /card/{number}
Ativa/Desativa um cartão do sistema.

**Request Body**
```json
{
    "active": true
}
```

**Response 200**
```json
{
    "id": 1,
    "number": "012730871",
    "clientId": 1,
    "active": true
}
```

 ### GET /card/{number}
Exibe um cartão do sistema

**Response 200**
```json
{
    "id": 1,
    "number": "012730871",
    "clientId": 1
}
```

 ## Requisições de pagamento:

 ### POST /payment
Cria um pagamento no sistema.

**Request Body**
```json
{
    "card_id": 1,
    "item": "cerveja",
    "cost": 10.5
}
```

**Response 201**
```json
{
    "id": 1,
    "card_id": 1,
    "item": "cerveja",
    "cost": 10.5
}
```

 ### GET /payment/{card_id}
Exibe os pagamentos de um Cartão (extrato)

**Response 200**
```json
{
    "number": "012730871",
    "invoice": [
	    {
            "id": 1,
            "card_id": 1,
            "item": "pizza",
            "cost": 20.5
        },
        {
            "id": 2,
            "card_id": 1,
            "item": "cerveja",
            "cost": 10.5
        }
    ]
}
```
