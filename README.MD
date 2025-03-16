<h1 align="center">
  <br />
  <img
    src="./_docs/assets/icon.png"
    alt="Mega Man Robots API"
    width="150"
  />
  <br />
  <b>Mega Man Robots API</b>
  <br />
  <sub
    ><sup><b>(MEGA-MAN-ROBOTS)</b></sup></sub
  >
  <br />
  <a
    href="https://github.com/felipeAguiarCode/MegaApiDotnetCore/actions/workflows/build.yml"
  >
    <img
      src="https://github.com/felipeAguiarCode/MegaApiDotnetCore/actions/workflows/build.yml/badge.svg"
      alt=""
    />
  </a>
  <a href="https://github.com/felipeAguiarCode/MegaApiDotnetCore/releases/latest">
    <img
      src="https://img.shields.io/github/v/release/felipeAguiarCode/MegaApiDotnetCore"
      alt="Latest Release"
    />
  </a>
</h1>

<p align="center">
  This .NET Core API is designed to serve JSON formatted data about bosses from
  the Mega Man series. It is a backend service built with .NET Core 3.1 and
  various modern dependencies for data management and API response handling.
  <br />
</p>

<p align="center">
  Developed with Entity Framework Core and other modern .NET technologies, this
  project aims to provide a robust API for accessing Mega Man robot data.
  <br />
</p>

<p align="center">
  <br />
  <img src="./_docs/assets/carbon.png" />
</p>

## API Endpoints

<table align="center">
  <tr>
    <th>Method</th>
    <th>Endpoint</th>
    <th>Description</th>
  </tr>
  <tr>
    <td>GET</td>
    <td>/api/v1/robots</td>
    <td>Returns a list of all robots</td>
  </tr>
  <tr>
    <td>GET</td>
    <td>/api/v1/robots/{id}</td>
    <td>Returns details of a specific robot by ID</td>
  </tr>
  <tr>
    <td>POST</td>
    <td>/api/v1/robots</td>
    <td>Endpoint to create a new robot entry</td>
  </tr>
</table>

## Techniques Used

<p align="center">
  - <b>Entity Framework Core:</b> ORM for data management.<br />
  - <b>RESTful API Design:</b> Ensures clear and effective communication
  endpoints.<br />
  - <b>Dependency Injection:</b> Used throughout to promote loose coupling and
  enhanced testability.<br />
</p>

## Dependencies

<table align="center">
  <tr>
    <th>Package</th>
    <th>Version</th>
    <th>Link</th>
  </tr>
  <tr>
    <td>Microsoft.EntityFrameworkCore</td>
    <td>3.1.8</td>
    <td>
      <a
        href="https://www.nuget.org/packages/Microsoft.EntityFrameworkCore/3.1.8"
        >NuGet</a
      >
    </td>
  </tr>
  <tr>
    <td>Microsoft.EntityFrameworkCore.Design</td>
    <td>3.1.8</td>
    <td>
      <a
        href="https://www.nuget.org/packages/Microsoft.EntityFrameworkCore.Design/3.1.8"
        >NuGet</a
      >
    </td>
  </tr>
  <tr>
    <td>Microsoft.EntityFrameworkCore.SqlServer</td>
    <td>3.1.8</td>
    <td>
      <a
        href="https://www.nuget.org/packages/Microsoft.EntityFrameworkCore.SqlServer/3.1.8"
        >NuGet</a
      >
    </td>
  </tr>
  <tr>
    <td>Newtonsoft.Json</td>
    <td>12.0.2</td>
    <td>
      <a href="https://www.nuget.org/packages/Newtonsoft.Json/12.0.2">NuGet</a>
    </td>
  </tr>
</table>

## :gear: Arch

```🌐
src
├── 📂 Controllers      [Routes for endpoints]
├── 📂 Models           [Database models]
├── 📂 Services         [Business rules]
├── 📂 Middlewares      [Intermediate functions between the HTTP request and the final server response]
├── 📂 Database         [Structures related to the database]
│   ├── 📂 DTOs             [Input Models and View Models (Data Transfer Objects)]
│   ├── 📂 EntityFramework  [Files related to the ORM Entity Framework]
│   │     ├── 📂 Context         [Entity context settings]
│   │     ├── 📂 Migrations      [Migrations for database updates]
│   ├── 📂 Repositories     [Repository pattern]
```
# Projeto: [MegaAPI]

## Visão Geral
Este projeto segue uma arquitetura organizada para manter um código limpo, modular e escalável. A estrutura de pastas facilita a separação de responsabilidades e o uso de boas práticas no desenvolvimento.

## Estrutura do Projeto

### 📂 Controllers (Controladores)
Os controladores são responsáveis por gerenciar as requisições HTTP. Eles definem as rotas e direcionam as solicitações para os serviços apropriados.

- **Objetivo:** Gerenciar as rotas e chamar os serviços necessários.
- **Exemplo de uso:** Receber uma requisição, validar os dados e enviar para a camada de serviços.

### 📂 Models (Modelos)
Contém as definições das entidades do banco de dados. Representa os dados que serão armazenados e manipulados.

- **Objetivo:** Definir a estrutura dos dados do sistema.
- **Exemplo de uso:** Classe `User` com propriedades como `id`, `name`, `email`.

### 📂 Services (Serviços)
Camada responsável pela lógica de negócio do sistema. Aqui são realizadas as regras de validação e processamento dos dados.

- **Objetivo:** Implementar a lógica de negócios.
- **Exemplo de uso:** Método para calcular descontos, processar pagamentos ou validar um cadastro.

### 📂 Middlewares (Intermediários)
São funções executadas entre a requisição e a resposta final. Usados para autenticação, logs, tratamento de erros, entre outros.

- **Objetivo:** Modificar ou validar requisições antes de serem processadas pelos controladores.
- **Exemplo de uso:** Middleware de autenticação para verificar tokens JWT.

### 📂 Database (Banco de Dados)
Contém todas as configurações e estrutura do banco de dados do projeto.

#### 📂 DTOs (Data Transfer Objects)
Define os modelos de entrada e saída de dados para garantir uma comunicação segura e organizada entre as camadas do sistema.

- **Objetivo:** Evitar a exposição direta dos modelos do banco de dados e facilitar a transformação de dados.
- **Exemplo de uso:** `UserDTO` para limitar os campos retornados na resposta de uma API.

#### 📂 EntityFramework (ORM - Mapeamento Objeto-Relacional)
Gerencia a comunicação entre a aplicação e o banco de dados utilizando o Entity Framework.

- **Objetivo:** Facilitar a manipulação de dados no banco sem necessidade de escrever SQL diretamente.
- **Subpastas:**
  - **Context:** Configuração do contexto do Entity Framework.
  - **Migrations:** Gerenciamento de versões do banco de dados.

#### 📂 Repositories (Repositórios)
Implementa o padrão Repository para abstrair o acesso ao banco de dados, garantindo um código mais modular e testável.

- **Objetivo:** Criar métodos específicos para consulta e manipulação de dados.
- **Exemplo de uso:** `UserRepository` com métodos como `GetById()`, `Create()`, `Update()`.

## Tecnologias Utilizadas
- **Linguagem:** [Defina a linguagem usada, ex: C#, TypeScript]
- **Banco de Dados:** [PostgreSQL, MySQL, MongoDB, etc.]
- **Frameworks:** [ASP.NET Core, Express.js, etc.]
- **ORM:** [Entity Framework, Sequelize, etc.]

## Como Executar o Projeto
1. Clone o repositório:
   ```sh
   git clone [URL do repositório]
   ```
2. Instale as dependências:
   ```sh
   [Comando para instalar dependências, ex: npm install]
   ```
3. Configure as variáveis de ambiente conforme o arquivo `.env.example`.
4. Execute as migrações do banco de dados:
   ```sh
   [Comando para rodar as migrações, ex: dotnet ef database update]
   ```
5. Inicie o servidor:
   ```sh
   [Comando para rodar o servidor, ex: dotnet run]
   ```

## Conclusão
Essa estrutura permite um desenvolvimento mais organizado, facilitando a manutenção e escalabilidade do sistema. Caso precise modificar ou expandir alguma funcionalidade, cada camada já está bem definida para auxiliar no processo.



## License This software is licensed under the terms of the [MIT]

⌨️ FelipeAguiar -
[Github](https://github.com/felipeAguiarCode)
