# Documentação da API Megaman

## Visão Geral
Este projeto é uma API desenvolvida em **.NET Core 3.1** que fornece informações sobre os chefes da franquia Megaman. O objetivo principal é fornecer um **backend** que disponibiliza os dados dos "Robots" no formato **JSON**.

### Exemplo de Resposta JSON
```json
{
  "Id": 1,
  "Code": "DLN/DRN-003",
  "Name": "Cutman",
  "HP": 150,
  "Picture": "https://vignette.wikia.nocookie.net/megaman/images/2/22/Cutman.png"
}
```

## Dependências do Projeto

| Dependência | Versão | Descrição |
|-------------|--------|------------|
| [Microsoft.EntityFrameworkCore](https://www.nuget.org/packages/Microsoft.EntityFrameworkCore/) | 3.1.8 | ORM para interação com banco de dados |
| [Microsoft.EntityFrameworkCore.Design](https://www.nuget.org/packages/Microsoft.EntityFrameworkCore.Design/) | 3.1.8 | Ferramentas para design de banco de dados |
| [Microsoft.EntityFrameworkCore.SqlServer](https://www.nuget.org/packages/Microsoft.EntityFrameworkCore.SqlServer/) | 3.1.8 | Provider para SQL Server |
| [Newtonsoft.Json](https://www.nuget.org/packages/Newtonsoft.Json/) | 12.0.2 | Biblioteca para manipulação de JSON |

## Estrutura do Projeto

```
.vs
.vscode
bin
Controllers
Database
Middlewares
Models
obj
Properties
Services
appsettings.Development.json
appsettings.json
global.json
MegamanApi.csproj
MegamanApi.sln
Program.cs
Startup.cs
```

## Endpoints da API

### 1. Listar todos os Robots
**GET** `api/v1/robots`

**Resposta:**
```json
[
  {
    "Id": 1,
    "Code": "DLN/DRN-003",
    "Name": "Cutman",
    "HP": 150,
    "Picture": "https://vignette.wikia.nocookie.net/megaman/images/2/22/Cutman.png"
  }
]
```

### 2. Buscar Robot por ID
**GET** `api/v1/robots/{id}`

**Resposta (200 OK):**
```json
{
  "Id": 1,
  "Code": "DLN/DRN-003",
  "Name": "Cutman",
  "HP": 150,
  "Picture": "https://vignette.wikia.nocookie.net/megaman/images/2/22/Cutman.png"
}
```
**Resposta (404 Not Found):**
```json
{
  "message": "Nenhum robo encontrado"
}
```

### 3. Criar um novo Robot
**POST** `api/v1/robots`

**Resposta:**
```json
{
  "message": "Robot criado com sucesso"
}
```

## Técnicas Utilizadas
- **ASP.NET Core 3.1**: Framework utilizado para desenvolvimento da API.
- **Entity Framework Core**: ORM para interação com banco de dados SQL Server.
- **Injeção de Dependência**: Implementação do padrão de projeto para gerenciamento de serviços.
- **RESTful**: Segue as boas práticas de desenvolvimento de APIs.
- **Tratamento de Erros**: Retorno de respostas padronizadas para erros.

---

Essa documentação pode ser expandida conforme necessário com mais detalhes sobre o modelo de dados, serviços e configuração do banco de dados.

