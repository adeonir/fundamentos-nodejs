<h1 align="center">
  <img src=".assets/logo-gostack.svg" atl="GoStack Bootcamp" />
</h1>

<h3 align="center">
  Desafio 5: Primeiro projeto Node.js
</h3>

<p align="center">
  Desafio desenvolvido durante o <a href="https://rocketseat.com.br/gostack">Bootcamp GoStack</a> da Rocketseat.
  <br />
  <br />
  <a href="#tecnologias">Tecnologias</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#sobre-o-desafio">Sobre o desafio</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#instalação-e-execução">Instalação e execução</a>
</p>

## Tecnologias

- [Node.js](https://nodejs.org/)
- [TypeScript](https://www.typescriptlang.org/)
- [Express](https://expressjs.com/)
- [ESLint](https://eslint.org/)
- [Prettier](https://prettier.io/)
- [Insomnia](https://insomnia.rest/)

## Sobre o desafio

Nesse desafio, eu criei uma aplicação para continuar treinando o que aprendi até agora no Node.js junto ao TypeScript, utilizando o conceito de models, repositories e services!

Essa é uma aplicação vai armazenar transações financeiras de entrada e saída, deve permitir o cadastro e a listagem dessas transações.

### Rotas da aplicação

- **`POST /transactions`**: A rota deve receber `title`, `value` e `type` dentro do corpo da requisição, sendo `type` o tipo da transação, que deve ser `income` para entradas (depósitos) e `outcome` para saidas (retiradas). Ao cadastrar uma nova transação, ela deve ser armazenada dentro de um objeto com o formato como o seguinte:

```json
{
  "id": "uuid",
  "title": "Salário",
  "value": 3000,
  "type": "income"
}
```

- **`GET /transactions`**: Essa rota deve retornar uma listagem com todas as transações que foram cadastradas até agora, junto com o valor de soma de entradas, retiradas e total de crédito. Essa rota deve retornar um objeto com o formato a seguir:

```json
{
  "transactions": [
    {
      "id": "uuid",
      "title": "Salário",
      "value": 4000,
      "type": "income"
    },
    {
      "id": "uuid",
      "title": "Freela",
      "value": 2000,
      "type": "income"
    },
    {
      "id": "uuid",
      "title": "Pagamento da fatura",
      "value": 4000,
      "type": "outcome"
    },
    {
      "id": "uuid",
      "title": "Cadeira Gamer",
      "value": 1200,
      "type": "outcome"
    }
  ],
  "balance": {
    "income": 6000,
    "outcome": 5200,
    "total": 800
  }
}
```

### Específicação dos testes

Para esse desafio temos os seguintes testes:

- **`should be able to create a new transaction`**: Para que esse teste passe, a aplicação deve permitir que uma transação seja criada, retornando um json com a transação criada.

- **`should be able to list the transactions`**: Para que esse teste passe, a aplicação deve retornar um objeto contendo todas as transações e também o balanço de income, outcome e total das transações que foram criadas até o momento.

- **`should not be able to create outcome transaction without a valid balance`**: Para que esse teste passe, a aplicação não deve permitir que uma transação do tipo `outcome` extrapole o valor total que o usuário tem em caixa, retornando uma resposta com código HTTP 400 e uma mensagem de erro no seguinte formato: `{ error: string }`

## Instalação e execução

```bash
# Clone esse repositório
$ git clone https://github.com/adeonir/gostack-fundamentos-nodejs fundamentos-nodejs

# Entre no diretório
$ cd fundamentos-nodejs

# Instale as dependências
$ yarn

# Rode a aplicação
$ yarn server

# Rode os testes
$ yarn test
```

## Licença

Esse projeto está sob a licença MIT.

---

Made with ♥️ by Adeonir Kohl
