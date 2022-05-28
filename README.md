<p align="center">
  <a href="http://nestjs.com/" target="blank"><img src="https://nestjs.com/img/logo-small.svg" width="200" alt="Nest Logo" /></a>
</p>

[circleci-image]: https://img.shields.io/circleci/build/github/nestjs/nest/master?token=abc123def456
[circleci-url]: https://circleci.com/gh/nestjs/nest


# Como usar nestjs com Prisma

**NestJS** é um framework para criar aplicações lado do servidor escaláveis em **nodejs**. Ele usa JavaScript moderno, suporta totalmente e é construído usando TypeScript, e combina elementos de programação reativa orientada a objetos, funcionais. Este tutorial demonstrará como usar o Nest e o Prisma para construir uma REST API. Como nota rápida, a demonstração foi realizada usando **node** v16.14.2, **npm** 8.9.0 e **Prisma** v3.14.0.


# Oque é Prisma?

O que é **Prisma**? **Prisma** é um (ORM) de última geração. Ele fornece um kit de ferramentas de banco de dados de código aberto para PostgreSQL, MySQL, SQL Server, SQLite e MongoDB (atualmente em pré-visualização), permitindo que os desenvolvedores construam aplicativos mais rápido e com menos erros. O **Prisma** fornece um método declarativo para definir os modelos de dados e as relações do seu aplicativo em um formato mais legível. Além disso, se você já tem um banco de dados, você não precisa passar pela dor de criar modelos de banco de dados do zero porque os recursos de introspecção do **Prisma** lidam com isso para você — é tão flexível.


# Para que serve o Prisma?

O **Prisma** melhora a segurança simplificando o acesso ao banco de dados, economizando e reduzindo o repetição de código no CRUD. O **Prisma** é fácil de integrar em sua estrutura preferida e é um kit de ferramentas de banco de dados ideal para criar APIs da Web confiáveis e escaláveis. O **Prisma** se integra rapidamente a vários frameworks, como GraphQL, Next.js, Nest, Apollo e Express.js

O **Prisma** aborda muitas deficiências dos ORMs tradicionais, como falta de segurança tipada, lógica mista de negócios e armazenamento e consultas imprevisíveis causadas por carregamento lento.

# Configuração inicial do projeto

Para começar com este tutorial, certifique-se de ter:

Node.js (v16.14.2) instalado
Postman instalado
Antes de começarmos a construir um aplicativo Nest, você precisa instalar o Nest CLI com o comando abaixo:

```bash
npm i -g @nestjs/cli
```

Aguarde a conclusão da instalação. Quando a instalação estiver concluída, crie um novo aplicativo Nest com o comando abaixo:

```bash
nest new prisma-api
```

Escolha npm como o gerenciador de pacotes preferido e pressione Enter. O aplicativo passará por alguns processos de instalação.

Assim que o npm tiver instalado todos os pacotes necessários para rodar a aplicação, mude o diretório para a pasta do projeto e execute o servidor com o comando abaixo:
  
  ```bash
  npm run start:dev
  ```

# Introdução ao Prisma

Este tutorial usa o Prisma v3.14.0. Instale o Prisma CLI como uma dependência de desenvolvimento com o comando abaixo:
  
  ```bash
  npm install prisma --save-dev
  ```

  Quando a instalação estiver concluída, invoque o Prisma CLI localmente usando npx com o comando abaixo:
  
  ```bash
  npx prisma
  ```

  Agora, crie sua configuração inicial do Prisma usando o comando Prisma init:
  
  ```bash
  npx prisma init
  ```

  O comando acima cria um novo diretório Prisma com os seguintes arquivos:

- **schema.prisma**: especifica sua conexão com o banco de dados e contém o esquema do banco de dados
- **.env**: um arquivo dotenv normalmente usado para armazenar suas credenciais de banco de dados em um grupo de variáveis de ambiente

# Conectando-se a um banco de dados

Com o Prisma instalado, a configuração no seu computador é bem fácil. Para a demonstração neste tutorial, vamos nos conectar a um banco de dados SQLite. Para começar, abra o arquivo **datasource/schema.prisma** e atualize o conteúdo com o snippet de código abaixo:

```prisma
generator client {
  provider = "prisma-client-js"
}

datasource db {
  provider = "sqlite"
  url = env("DATABASE_URL")
}
```

No trecho acima, especificamos o sqlite como nosso provedor de banco de dados. Agora, modifique o arquivo .env para especificar o local do arquivo de banco de dados.

```.env
DATABASE_URL="file:./todos.sqlite"
```