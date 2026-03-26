# UsuariosApi

## 🧾 Descrição do Projeto

O projeto UsuariosApi é uma aplicação backend em .NET 9 para controle de usuários, permitindo cadastro, login e acesso autorizado baseado em idade mínima. O projeto utiliza Entity Framework Core com MySQL, ASP.NET Core Identity para gerenciamento de usuários, JWT para autenticação, e AutoMapper para mapeamento de objetos.

## 🚀 Funcionalidades

- Cadastro de usuários com validação de dados.
- Login de usuários com geração de token JWT.
- Acesso autorizado baseado em idade mínima.
- Estrutura organizada com DTOs para criação e login.

## 🛠 Tecnologias

- .NET 9
- MySQL
- Entity Framework Core
- ASP.NET Core Identity
- JWT
- AutoMapper
- Swagger/OpenAPI

## 📁 Estrutura do Projeto

UsuariosApi/
- ├── Controllers/                 -> Controladores da API 
- ├── Data/                        -> Contexto do banco e DTOs
- ├── Migrations/                  -> Migrações do Entity Framework
- ├── Models/                      -> Entidades do domínio
- ├── Profiles/                    -> Perfis do AutoMapper
- ├── Properties/                  -> Configurações do projeto
- ├── Services/                    -> Serviços
- ├── Authorization/               -> Autorização customizada
- ├── appsettings.json             -> Configurações da aplicação
- ├── Program.cs                   -> Ponto de entrada da aplicação

## ⚙️ Pré-requisitos

- .NET 9 SDK
- MySQL Server
- Ferramenta de testes de API: Postman ou navegador para Swagger
- Git

## 🛠 Instalação e Setup

Configure a connection string no appsettings.Development.json (ou appsettings.json):
```
"ConnectionStrings": {
    "UsuarioConnection": "Server=localhost;Database=usuariodb;User=root;Password=root;"
}
```

Crie e atualize o banco de dados:
```
dotnet ef migrations add InitialCreate
dotnet ef database update
```

Execute a API:
```
dotnet run
```

Acesse a documentação Swagger:
```
http://localhost:5126/swagger
```

## 🧑‍💻 Testando os Endpoints

### Usuários
Cadastrar usuário:
```
POST /usuario/cadastro
{
  "username": "usuario_exemplo",
  "dataNascimento": "2000-01-01T00:00:00",
  "password": "Senha123!",
  "rePassword": "Senha123!"
}
```

Login de usuário:
```
POST /usuario/login
{
  "username": "usuario_exemplo",
  "password": "Senha123!"
}
```

### Acesso
Acessar endpoint autorizado (requer token JWT no header Authorization):
```
GET /acesso
```
