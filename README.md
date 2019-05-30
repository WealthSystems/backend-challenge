# Desafio Wealth Systems para back-end

Este desafio visa avaliar seus conhecimentos no desenvolvimento de aplicações back-end. Este documento descreve o que esperamos e recomendamos na sua implementação.

A aplicação proposta neste desafio é uma API de produtos e pedidos de compras que possam ser confirmados e cancelados. Abaixo estão relacionados os endpoints que gostariamos de ver na aplicação e alguns exemplos de resposta.

Não é necessário que você entregue 100% da aplicação. Ainda que iremos avaliar o quanto você implementou, não é o indicador mais importante na nossa avaliação.  A ideia principal deste desafio é que ele nos permita conhecer como você desenvolve e quais são os seus conhecimentos e experiências.

----------

- Listagem dos produtos cadastrados

Resposta:

```json
[
  {
    "id": 25,
    "name": "Orange juice"
  },
  {
    "id": 26,
    "name": "Apple juice"
  }
]
```

- Consulta dos detalhes de um produto usando o identificador

Resposta:

```json
{
  "id": 25,
  "name": "Orange juice",
  "description": "Delicious natural orange juice. No addition of apples to fool consumers.",
  "barcode": "8901072002478",
  "manufacturer": {
    "id": 2,
    "name": "Quality farm goods"
  },
  "unitPrice": 18.55
}
```

- Inserção de novos produtos

Solicitação:

```json
{
  "name": "Grape juice",
  "description": "Natural grape juice",
  "barcode": "7002085002679",
  "manufacturer": {
    "id": 2
  },
  "unitPrice": 25.89
}
```

- Atualização de produtos usando o seu identificador

Solicitação:

```json
{
  "name": "Grape juice",
  "description": "Natural grape juice",
  "barcode": "7002085002679",
  "manufacturer": {
    "id": 2
  },
  "unitPrice": 25.89
}
```

Resposta:

```json
{
  "id": 27,
  "name": "Grape juice",
  "description": "Natural grape juice",
  "barcode": "7002085002679",
  "manufacturer": {
    "id": 2,
    "name": "Quality farm goods"
  },
  "unitPrice": 25.89
}
```

- Remoção de um produto
- Cadastro de um pedido

Solicitação:

```json
{
  "products": [
    { "id": 25, "units": 2 },
    { "id": 26, "units": 2.25 },
    { "id": 29, "units": 1 },
  ],
  "consumer": {
    "name": "John Doe",
    "phone": "+554512345678",
    "email": "some@one.com"
  },
  "payment": {
    "mode": "bank slip",
    "installments": 3
  },
  "delivery": {
    "mode": "in-store withdrawal"
  }
}
```

- Consulta de um pedido

Resposta:

```json
{
  "id": 2,
  "status": "pending confirmation",
  "products": [
    { 
      "id": 25, 
      "name": "Orange juice", 
      "units": 2, 
      "unitPrice": 10, 
      "amount": 20 
    }, { 
      "id": 26, 
      "name": "Apple juice", 
      "units": 2.25, 
      "unitPrice": 15.50, 
      "amount": 34.87 
    }, { 
      "id": 29, 
      "name": "Grape juice", 
      "units": 1, 
      "unitPrice": 36.65, 
      "amount": 36.65 
    }
  ],
  "consumer": {
    "id": 3,
    "name": "John Doe",
    "phone": "+554512345678",
    "email": "some@one.com"
  },
  "payment": {
    "mode": "bank slip",
    "amount": 91.52,
    "installments": 3,
    "installmentValue": 30.51
  },
  "delivery": {
    "mode": "in-store withdrawal"
  }
}
```

- Cancelamento de um pedido

- Confirmação de um pedido

----------

## Requisitos

- README com instruções de uso da aplicação
- Versionamento usando Git
- Seguir a especificação REST usando JSON

## Recomendações

Os itens abaixo são aqueles geralmente utilizados em nossos projetos. Eles não são obrigatórios, mas podem te ajudar a entender o nosso dia-a-dia.

- Spring Boot ou Eclipse MicroProfile como framework de fundação
- Java 8 ou superior
- Banco de dados PostgreSQL 9.6 ou superior
- BeanValidation 2.0 para validação dos dados
- Código e documentação em Inglês
- Automação de build com o Gradle

## O que será analisado

- Clean code, SOLID e DRY
- Testes unitários e de integração
- Design patterns

## Diferenciais

Sinta-se livre para usar ferramentas e bibliotecas que podem agregar valor ao seu projeto. Anexe ao README um breve resumo sobre cada uma e por que você optou por utilizar ela.

Além disso, também iremos considerar como diferenciais os seguintes itens:

- CI/CD
- Docker
- OpenAPI/Swagger
- Versionamento do banco de dados
- i18n
- Tratamento de erros
- Paginação, ordenação e projeção

----------


Happy coding. 🙂 

