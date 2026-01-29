# Plataforma de Gerenciamento de Clientes - Facilita Juridico

Aplicacao fullstack para gerenciamento de clientes de um escritorio juridico, com cadastro, busca, listagem paginada e calculo de rota otimizada de visitacao.

## Tech Stack

**Frontend:** React 18, TypeScript, Vite, Tailwind CSS, Shadcn UI (Radix), Zustand, Axios, Sonner (toasts)

**Backend:** Node.js, Express, TypeScript, PostgreSQL (pg), Zod (validacao), Vitest (testes)

**Infra:** Docker, Docker Compose

## Funcionalidades

- Cadastro de clientes com validacao de dados via Zod
- Listagem paginada com busca por nome, email ou telefone
- Exclusao de clientes
- Calculo de rota otimizada para visitacao de clientes selecionados
- Dark mode
- Seed de dados com Faker.js para testes

## Arquitetura

```
backend/
  src/
    http/controllers/    # Controllers (createClient, getClients, deleteClient, calculateRoute)
    services/            # Regras de negocio
    repositories/        # Camada de acesso a dados (PostgreSQL)
    schemas/             # Validacao com Zod
    database/            # Migrations, seed e conexao
    Error/               # Tratamento de erros customizado

frontend/
  src/
    components/          # Componentes React (TableClient, Search, Pagination, DrawerForms, RouteDialog)
    components/ui/       # Componentes Shadcn UI
    components/theme/    # Tema dark/light
```

## Como Rodar

### Pre-requisitos
- Node.js 18+
- Docker e Docker Compose

### Backend

```bash
cd backend
npm install
cp .env.example .env       # ajuste as variaveis se necessario
docker compose up -d        # sobe o PostgreSQL
npm run migrate             # cria as tabelas
npm run seed                # (opcional) popula com 10 registros
npm run dev                 # inicia na porta 3333
```

### Frontend

```bash
cd frontend
npm install
cp .env.example .env
npm run dev                 # inicia em http://localhost:5173
```

### Testes

```bash
cd backend
npm test                    # roda testes com Vitest
npm run test:watch          # modo watch
```

## Autor

**Lucas Silva** - [LinkedIn](https://www.linkedin.com/in/lucashs94/) | [GitHub](https://github.com/lucashs94) | h7.lucas@gmail.com
