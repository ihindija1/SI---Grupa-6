# Sport.ba

A full-stack sports league and facility management platform developed by a student team for the Software Engineering course at the Faculty of Electrical Engineering, University of Sarajevo.

## Overview

Sport.ba connects players, coaches, organizers, facility owners, and administrators in one role-based system. It supports the complete workflow from team registration and facility booking to fixtures, results, standings, statistics, notifications, and training sessions.

## Key features

- Registration, login, password recovery, and role-based authorization
- Team creation, membership, applications, and favorite teams
- League and competition management
- Match scheduling, results, tables, and player/team statistics
- Sports facility listings, available terms, bookings, and waiting lists
- Individual and group training reservations
- Real-time notifications with Socket.IO
- PDF report generation
- Background reservation processing with Bull/BullMQ and Redis
- AI-assisted match prediction service
- Administrative user and role management

## Tech stack

### Frontend

- React 19 and Vite
- React Router, TanStack Query, Axios
- Tailwind CSS, Framer Motion
- Vitest and Testing Library

### Backend

- Node.js and Express
- PostgreSQL with Prisma ORM
- JWT authentication, bcrypt, Zod validation
- Socket.IO for real-time updates
- Redis and Bull/BullMQ for background work
- Jest and Supertest

### AI and infrastructure

- Python and FastAPI prediction service
- Docker and Docker Compose
- Nginx reverse proxy
- Railway/Render deployment configuration

## Repository structure

```text
SI---Grupa-6/
├── Projekat/
│   ├── frontend/       React client
│   ├── backend/        Express API, Prisma schema, and tests
│   ├── ai-service/     FastAPI prediction service
│   ├── nginx/          Reverse-proxy configuration
│   └── docker-compose.yml
├── Sprint1/ ... Sprint11/
│                       Planning, architecture, testing, reviews, and release documentation
└── README.md
```

## Getting started with Docker

### Prerequisites

- Docker
- Docker Compose

1. Move into the application directory:

```bash
cd Projekat
```

2. Create the required local environment files from the provided examples:

```bash
cp backend/.env.example backend/.env
```

Configure `DATABASE_URL`, `JWT_SECRET`, `FRONTEND_URL`, and optional email settings. Create the AI service environment file if required by that service.

3. Start the stack:

```bash
docker compose up --build
```

The default local endpoints are:

- Frontend: [http://localhost](http://localhost)
- Backend API: [http://localhost:3000](http://localhost:3000)
- AI service: [http://localhost:8000](http://localhost:8000)

## Local development

### Backend

```bash
cd Projekat/backend
npm install
npx prisma generate
npx prisma migrate dev
npm run dev
```

### Frontend

```bash
cd Projekat/frontend
npm install
npm run dev
```

PostgreSQL and Redis must be available, and the backend environment variables must point to them.

## Testing

Backend tests:

```bash
cd Projekat/backend
npm test
npm run test:coverage
```

Frontend tests:

```bash
cd Projekat/frontend
npm test
```

The repository also contains sprint-level proof of testing, test strategy, release notes, known issues, and the final user manual.

## Engineering process

The project was developed across eleven documented sprints. The repository includes the product backlog, user stories, architecture decisions, risk register, API documentation, sprint goals and retrospectives, testing evidence, deployment procedures, and release documentation.

## What this project demonstrates

- Building a multi-role full-stack application in a team environment
- Designing a large relational domain with Prisma and PostgreSQL
- Implementing authentication, real-time events, queues, and scheduled work
- Testing frontend and backend behavior
- Working through a complete iterative software engineering process

## Team

Developed by Group 6 for the Software Engineering course. This repository is a fork retained as part of Ilma Hindija's academic portfolio.
