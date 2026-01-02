# TeslaFolio - Portfolio Application

## Overview

TeslaFolio is a Tesla-inspired portfolio and dashboard application built with a modern full-stack architecture. It showcases projects, displays statistics, and features a rewards/gamification system. The application uses a dark, minimalist design aesthetic inspired by Tesla's brand identity, with smooth animations and a futuristic UI.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture
- **Framework**: React 18 with TypeScript
- **Routing**: Wouter (lightweight React router)
- **State Management**: TanStack React Query for server state
- **Styling**: Tailwind CSS with CSS variables for theming
- **UI Components**: shadcn/ui component library (Radix UI primitives)
- **Animations**: Framer Motion for page transitions and scroll effects
- **Icons**: Lucide React

The frontend follows a component-based architecture with:
- Reusable UI components in `client/src/components/ui/`
- Feature components in `client/src/components/`
- Custom hooks in `client/src/hooks/`
- Pages in `client/src/pages/`

Path aliases are configured:
- `@/*` → `./client/src/*`
- `@shared/*` → `./shared/*`
- `@assets` → `./attached_assets/`

### Backend Architecture
- **Runtime**: Node.js with Express
- **Language**: TypeScript (ESM modules)
- **Build Tool**: Vite for frontend, esbuild for server bundling
- **API Style**: RESTful endpoints defined in `shared/routes.ts`

The server handles:
- Static file serving in production
- Vite dev server integration in development
- API routes for projects, stats, and rewards

### Data Layer
- **ORM**: Drizzle ORM
- **Database**: PostgreSQL
- **Schema Location**: `shared/schema.ts`
- **Migrations**: `./migrations/` directory via `drizzle-kit`

Database tables:
- `projects`: Portfolio projects with title, description, image, tech stack
- `stats`: Dashboard statistics (CO2 saved, miles driven, etc.)
- `rewards`: Gamification rewards with points system

### Shared Code
The `shared/` directory contains code used by both frontend and backend:
- `schema.ts`: Drizzle table definitions and Zod schemas
- `routes.ts`: API route definitions with type-safe response schemas

## External Dependencies

### Database
- PostgreSQL via `DATABASE_URL` environment variable
- Connection pooling with `pg` driver
- Session storage with `connect-pg-simple`

### Third-Party Services
- **Chatway**: Live chat widget embedded in `client/index.html`
- **Google Fonts**: Inter, Orbitron, DM Sans, Fira Code, Geist Mono

### Key npm Packages
- `drizzle-orm` / `drizzle-kit`: Database ORM and migrations
- `@tanstack/react-query`: Data fetching and caching
- `framer-motion`: Animations
- `zod` / `drizzle-zod`: Schema validation
- `express-session`: Session management
- Full shadcn/ui component suite via Radix UI primitives

### Development Tools
- Replit-specific Vite plugins for development overlay and cartographer
- TypeScript with strict mode enabled
- PostCSS with Tailwind and Autoprefixer