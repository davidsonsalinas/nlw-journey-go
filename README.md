# Journey API Project

Este projeto foi desenvolvido durante a imersão NLW Next Level da Rocketseat, utilizando Go, Docker, PostgreSQL e várias outras ferramentas e bibliotecas para criar uma API completa.

## Tecnologias Utilizadas

- **Linguagem:** Go 1.22.4
- **Bibliotecas:**
  - github.com/discord-gophers/goapi-gen
  - github.com/getkin/kin-openapi
  - github.com/go-chi/chi
  - github.com/go-chi/render
  - github.com/google/uuid
  - github.com/jackc/pgx/v5
  - go.uber.org/zap
  - ... e outras listadas no go.mod
- **Banco de Dados:** PostgreSQL
- **Gerenciamento de Banco de Dados:** pgAdmin
- **Contêinerização:** Docker, Docker Compose
- **Fake Mail:** Mailpit

## Pré-requisitos

- Docker
- Docker Compose

## Como Rodar o Projeto

1. Clone o repositório:
   ```sh
   git clone https://github.com/seu-usuario/journey.git
   cd journey

### Crie um arquivo .env na raiz do projeto e defina as variáveis de ambiente:
.env

    JOURNEY_DATABASE_USER=seu_usuario
    JOURNEY_DATABASE_NAME=seu_banco
    JOURNEY_DATABASE_PASSWORD=sua_senha
    PGADMIN_DEFAULT_EMAIL=admin@admin.com
    PGADMIN_DEFAULT_PASSWORD=password

### Suba os contêineres:
    docker-compose up


### Acesse os serviços:
    API: http://localhost:8080
    pgAdmin: http://localhost:8081
    Mailpit: http://localhost:8025

### Estrutura do Projeto
    .
    ├── cmd
    │   └── journey
    │       └── main.go
    ├── internal
    │   ├── api
    │   │   ├── handlers
    │   │   └── spec
    │   ├── pgstore
    │   │   ├── migrations
    │   │   └── sqlc.yaml
    │   └── utils
    ├── go.mod
    ├── go.sum
    └── Dockerfile


### Comandos Importantes
O projeto utiliza alguns comandos go generate para facilitar a geração de código e migrações de banco de dados. Estes comandos são executados automaticamente, mas podem ser executados manualmente, se necessário.

### Gerar código da API:
    go generate ./internal/api/spec/journey.spec.json


### Migrar banco de dados:
    go generate ./internal/pgstore/migrations/tern.conf


### Gerar código SQL:
    go generate -f ./internal/pgstore/sqlc.yaml
