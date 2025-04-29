# API Integration Tests - Fakerestapi (Books)

Este projeto realiza testes de integração automatizados para a API [Fakerestapi](https://fakerestapi.azurewebsites.net/index.html), focando nos endpoints relacionados a **Books**. Utiliza as ferramentas **Jest**, **PactumJS**, **Prettier**, **ESLint** e integração com **SonarQube** para garantir qualidade, padronização e cobertura dos testes.

## Tecnologias Utilizadas

- [Jest](https://jestjs.io/) - Test runner
- [PactumJS](https://pactumjs.github.io/) - Framework para testes de API
- [Prettier](https://prettier.io/) - Formatação de código
- [ESLint](https://eslint.org/) - Linter para JavaScript
- [SonarQube](https://www.sonarqube.org/) - Análise de qualidade de código

## Endpoints Testados

Os principais endpoints testados deste projeto são:

- `GET /api/v1/Books` - Lista todos os livros
- `POST /api/v1/Books` - Cria um novo livro
- `GET /api/v1/Books/{id}` - Busca um livro pelo ID
- `PUT /api/v1/Books/{id}` - Atualiza um livro pelo ID
- `DELETE /api/v1/Books/{id}` - Remove um livro pelo ID

Também podem ser testados endpoints relacionados a autores e capas de livros, como:

- `GET /api/v1/Authors/authors/books/{idBook}` - Lista autores de um livro
- `GET /api/v1/CoverPhotos/books/covers/{idBook}` - Lista capas de um livro

A documentação completa da API pode ser encontrada [aqui](https://fakerestapi.azurewebsites.net/index.html).

## Pré-requisitos

- Node.js `v20` ou superior
- npm

## Instalação

Clone o repositório e instale as dependências:

```sh
git clone https://github.com/seu-usuario/seu-repo.git
cd seu-repo
npm install
```

## Como executar os testes

Execute os testes com o comando:

```sh
npm test
```

Ou, para rodar o pipeline completo (incluindo lint e prettier):

```sh
npm run ci
```

Após a execução, os relatórios de testes podem ser encontrados na pasta `./output`.

## Análise de Qualidade

A análise de qualidade do código é feita via SonarQube. Consulte o pipeline CI para detalhes.

## Descrição dos Testes Automatizados

Abaixo estão as explicações dos testes implementados no arquivo `fakerestapi.spec.ts`:

- **Buscar todos os livros:**  
  Verifica se a API retorna uma lista de livros no formato esperado.

- **Buscar um livro pelo ID:**  
  Garante que é possível recuperar um livro específico pelo seu ID.

- **Buscar um livro inexistente:**  
  Testa se a API retorna o status 404 ao buscar um livro que não existe.

- **Criar um novo livro:**  
  Valida se um novo livro pode ser criado com sucesso e se os dados retornados estão corretos.

- **Criar um livro com dados inválidos:**  
  Verifica se a API retorna erro ao tentar criar um livro com dados inválidos.

- **Atualizar um livro existente:**  
  Testa se é possível atualizar os dados de um livro já cadastrado.

- **Deletar um livro:**  
  Garante que um livro pode ser removido da base de dados.

- **Buscar autores de um livro:**  
  Verifica se a API retorna corretamente os autores associados a um livro.

- **Buscar autores de um livro inexistente:**  
  Testa se a API retorna um array vazio ao buscar autores de um livro que não existe.

- **Buscar capas de um livro:**  
  Valida se a API retorna as capas associadas a um livro específico.

## Referências

- [Fakerestapi Swagger](https://fakerestapi.azurewebsites.net/index.html)
- [PactumJS Docs](https://pactumjs.github.io/)
- [Jest Docs](https://jestjs.io/docs/getting-started)
