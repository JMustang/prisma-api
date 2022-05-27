<p align="center">
  <a href="http://nestjs.com/" target="blank"><img src="https://nestjs.com/img/logo-small.svg" width="200" alt="Nest Logo" /></a>
</p>

[circleci-image]: https://img.shields.io/circleci/build/github/nestjs/nest/master?token=abc123def456
[circleci-url]: https://circleci.com/gh/nestjs/nest

 
    

## Instalação

```bash
$ npm install -g @nestjs/cli
```

## Rodando o app

```bash
# Desenvolvimento
$ npm run start

# watch mode
$ npm run start:dev

# modo de produção
$ npm run start:prod
```

## testes

```bash

```bash
# Teste unitario
$ npm run test

# e2e tests
$ npm run test:e2e

# test coverage
$ npm run test:cov
```

# Como usar nestjs com Prisma

**NestJS** é um framework para criar aplicações lado do servidor escaláveis em **nodejs**. Ele usa JavaScript moderno, suporta totalmente e é construído usando TypeScript, e combina elementos de programação reativa orientada a objetos, funcionais. Este tutorial demonstrará como usar o Nest e o Prisma para construir uma REST API. Como nota rápida, a demonstração foi realizada usando **node** v16.14.2, **npm** 8.9.0 e **Prisma** v3.14.0.


# Oque é Prisma?

O que é **Prisma**? **Prisma** é um (ORM) de última geração. Ele fornece um kit de ferramentas de banco de dados de código aberto para PostgreSQL, MySQL, SQL Server, SQLite e MongoDB (atualmente em pré-visualização), permitindo que os desenvolvedores construam aplicativos mais rápido e com menos erros. O **Prisma** fornece um método declarativo para definir os modelos de dados e as relações do seu aplicativo em um formato mais legível. Além disso, se você já tem um banco de dados, você não precisa passar pela dor de criar modelos de banco de dados do zero porque os recursos de introspecção do **Prisma** lidam com isso para você — é tão flexível.
