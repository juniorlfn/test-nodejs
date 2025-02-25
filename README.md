### Backend Test

##### Knex (Query Builder):

`npm install knex -g` instalação global.

`knex migrate:up` executar as migrations.

##### Testes automatizados (integração):

`npm install` instalar as dependências do projeto.

`npm run test` executar os testes.

##### Executar projeto em desenvolvimento:

`npm install` instalar as dependências do projeto.

`npm install nodemon -g` instalação global do nodemon.

`npm run dev` executar o projeto.

##### Executar projeto com Docker:

`docker build -t api-server .` para construir a imagem.

`docker run -d -p 3000:3000 api-server` para iniciar o serviço.

[![Build Status](https://travis-ci.org/belezanaweb/test-nodejs.svg?branch=master)](https://travis-ci.org/belezanaweb/test-nodejs)

Esta é uma avaliação básica de código.

O objetivo é conhecer um pouco do seu conhecimento/prática de RESTful e NodeJS.

Recomendamos que você não gaste mais do que 4 - 6 horas.

Faça um fork deste repositório.

Ao finalizar o teste, submeta um pull request para o repositório que nosso time será notificado.

### Tarefas

Com a seguinte representação de produto:

```json
{
  "sku": 43264,
  "name": "L'Oréal Professionnel Expert Absolut Repair Cortex Lipidium - Máscara de Reconstrução 500g",
  "inventory": {
    "quantity": 15,
    "warehouses": [
      {
        "locality": "SP",
        "quantity": 12,
        "type": "ECOMMERCE"
      },
      {
        "locality": "MOEMA",
        "quantity": 3,
        "type": "PHYSICAL_STORE"
      }
    ]
  },
  "isMarketable": true
}
```

Crie endpoints para as seguintes ações:

- [x] Criação de produto onde o payload será o json informado acima (exceto as propriedades **isMarketable** e **inventory.quantity**)

- [x] Edição de produto por **sku**

- [x] Recuperação de produto por **sku**

- [x] Deleção de produto por **sku**

### Requisitos

- [x] Toda vez que um produto for recuperado por **sku** deverá ser calculado a propriedade: **inventory.quantity**

        A propriedade inventory.quantity é a soma da quantity dos warehouses

- [x] Toda vez que um produto for recuperado por **sku** deverá ser calculado a propriedade: **isMarketable**

        Um produto é marketable sempre que seu inventory.quantity for maior que 0

- [x] Caso um produto já existente em memória tente ser criado com o mesmo **sku** uma exceção deverá ser lançada

        Dois produtos são considerados iguais se os seus skus forem iguais

- [x] Ao atualizar um produto, o antigo deve ser sobrescrito com o que esta sendo enviado na requisição

        A requisição deve receber o sku e atualizar com o produto que tbm esta vindo na requisição

### Dicas

- [x] Os produtos podem ficar em memória, não é necessário persistir os dados
- [x] Testes são sempre bem-vindos :smiley:
