# RetroGames — Marketplace de Jogos Clássicos

Repositório oficial do projeto de desenvolvimento web **RetroGames Marketplace**.

---

## 👥 Integrantes do Grupo

| Nome Completo | Matrícula / E-mail | GitHub |
| :--- | :--- | :--- |
| Eurico Santiago Climaco Rodrigues | [san14311982@gmail.com] | 2024.1.08.036  |'
| *Membro 2* | | |
| *Membro 3* | | |
| *Membro 4* | | |
| *Membro 5* | | |

> *Substitua os campos acima com os dados oficiais do grupo.*

---

## 🛠️ Stack Tecnológica

O projeto adota uma stack bem definida com foco acadêmico e boas práticas de arquitetura em camadas:

- **Backend:** .NET 10 (ASP.NET Core Web API com Controllers)
- **Acesso a Dados:** ADO.NET puro com `MySqlConnector`
- **Validação:** FluentValidation
- **Testes Unitários:** xUnit + Moq
- **Banco de Dados:** MySQL 8
- **Frontend:** React + Vite + Bootstrap + Axios
- **Ambiente de Banco:** Docker & Docker Compose

*(Nota: Conforme diretrizes da disciplina, **não** utilizamos Entity Framework, Dapper, JWT, TypeScript ou Tailwind).*

---

## 🚀 Fases do Projeto

### Fase 1: Preparação do Ambiente e Banco com Docker (Em Andamento)

Nesta etapa inicial, padronizamos as dependências para que todos os 5 integrantes do grupo trabalhem no mesmo ambiente sem conflitos de versão.

#### Por que usamos Docker para o MySQL?
1. **Evitar conflitos de instalação local:** Impede divergências de versão do MySQL (ex.: MySQL 5.7 vs 8.0) e problemas com serviços do sistema operacional já existentes.
2. **Setup em um comando:** Qualquer membro do grupo pode clonar o repositório e subir o banco de dados idêntico com apenas `docker compose up -d`.
3. **Isolamento e Segurança:** O contêiner já sobe com o banco `retrogames_db`, usuário dedicado para a aplicação (`retrogames_user`) e permissões corretas, respeitando o arquivo de diretrizes.

#### Como iniciar o ambiente de desenvolvimento

##### 1. Pré-requisitos instalados na máquina:
- [Docker e Docker Compose](https://www.docker.com/)
- [.NET SDK 10](https://dotnet.microsoft.com/)
- [Node.js 22 (LTS)](https://nodejs.org/)
- [MySQL Workbench](https://www.mysql.com/products/workbench/) (solicitado para modelagem e consultas)

##### 2. Subindo o banco de dados:
Na raiz do repositório, execute:
```bash
docker compose up -d
```
Para parar o banco sem perder os dados:
```bash
docker compose down
```

##### 3. Conexão via MySQL Workbench:
- **Hostname:** `localhost` (ou `127.0.0.1`)
- **Port:** `3306`
- **Para administração/scripts:**
  - **Username:** `root`
  - **Password:** `root_dev_password`
- **Para a aplicação:**
  - **Username:** `retrogames_user`
  - **Password:** `retrogames_dev_password`
  - **Default Schema:** `retrogames_db`

---

## 🤖 Uso de Inteligência Artificial no Grupo

Para garantir que todos os membros e suas respectivas IAs permaneçam alinhados e evitem divergências de código durante Pull Requests:

1. **Diretrizes e Regras:** Leia atentamente o arquivo [.agents/agents.md](.agents/agents.md). Ele dita a arquitetura em camadas, regras de banco e convenções.
2. **Contexto entre Máquinas:** O arquivo [.agents/CONTEXTO_AGENTES.md](.agents/CONTEXTO_AGENTES.md) documenta o histórico de decisões e o estado de cada fase. Toda vez que um integrante abrir um PR ou finalizar uma tarefa, esse arquivo deve ser sincronizado.

