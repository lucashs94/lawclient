# Lawclient

A fullstack application for managing law firm clients, featuring registration, search, paginated listing, and optimized visitation route calculation.

## Tech Stack

**Frontend:** React 18, TypeScript, Vite, Tailwind CSS, Shadcn UI (Radix), Zustand, Axios, Sonner (toasts)

**Backend:** Node.js, Express, TypeScript, PostgreSQL (pg), Zod (validation), Vitest (tests)

**Infrastructure:** Docker, Docker Compose

## Features

- Client registration with data validation via Zod
- Paginated listing with search by name, email, or phone
- Client deletion
- Optimized route calculation for visiting selected clients
- Dark mode
- Data seeding with Faker.js for testing

## Architecture

```
backend/
  src/
    http/controllers/    # Controllers (createClient, getClients, deleteClient, calculateRoute)
    services/            # Business logic
    repositories/        # Data access layer (PostgreSQL)
    schemas/             # Validation with Zod
    database/            # Migrations, seed, and connection
    Error/               # Custom error handling

frontend/
  src/
    components/          # React components (TableClient, Search, Pagination, DrawerForms, RouteDialog)
    components/ui/       # Shadcn UI components
    components/theme/    # Dark/light theme
```

## Getting Started

### Prerequisites
- Node.js 18+
- Docker and Docker Compose

### Backend

```bash
cd backend
npm install
cp .env.example .env       # adjust variables if needed
docker compose up -d        # start PostgreSQL
npm run migrate             # create the tables
npm run seed                # (optional) populate with 10 records
npm run dev                 # starts on port 3333
```

### Frontend

```bash
cd frontend
npm install
cp .env.example .env
npm run dev                 # starts at http://localhost:5173
```

### Tests

```bash
cd backend
npm test                    # run tests with Vitest
npm run test:watch          # watch mode
```