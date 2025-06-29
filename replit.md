# Replit.md

## Overview

This is a full-stack web application built with a modern TypeScript stack featuring a React frontend and Express backend. The application appears to be a space/aerospace industry website with contact form functionality. It uses Drizzle ORM for database operations with PostgreSQL, shadcn/ui for the component library, and TanStack Query for state management.

## System Architecture

### Frontend Architecture
- **Framework**: React 18+ with TypeScript
- **Routing**: Wouter (lightweight client-side routing)
- **Styling**: Tailwind CSS with CSS variables for theming
- **UI Components**: shadcn/ui component library (Radix UI primitives)
- **State Management**: TanStack React Query for server state
- **Forms**: React Hook Form with Zod validation
- **Build Tool**: Vite with TypeScript support

### Backend Architecture
- **Runtime**: Node.js with TypeScript
- **Framework**: Express.js
- **Database**: PostgreSQL via Neon Database
- **ORM**: Drizzle ORM with Drizzle Kit for migrations
- **Validation**: Zod schemas shared between frontend and backend
- **Development**: tsx for TypeScript execution

### Data Storage Solutions
- **Primary Database**: PostgreSQL (configured for Neon Database)
- **ORM**: Drizzle ORM with type-safe queries
- **Migrations**: Drizzle Kit for schema management
- **Storage Implementation**: DatabaseStorage class using PostgreSQL

## Key Components

### Database Schema
- **Users Table**: Basic user authentication (id, username, password)
- **Contact Inquiries Table**: Contact form submissions (id, name, email, company, projectType, message, createdAt)

### API Endpoints
- `POST /api/contact` - Submit contact form
- `GET /api/contact-inquiries` - Retrieve all contact inquiries (admin endpoint)

### Frontend Pages
- **Home Page**: Main landing page with space/aerospace theme and contact form
- **404 Page**: Custom not found page

### Shared Types and Validation
- Zod schemas for data validation shared between client and server
- TypeScript types auto-generated from Drizzle schema
- Form validation using React Hook Form with Zod resolvers

## Data Flow

1. **Contact Form Submission**:
   - User fills out contact form on frontend
   - Form validates using shared Zod schema
   - Data sent to `/api/contact` endpoint
   - Backend validates and stores in database
   - Success/error feedback via toast notifications

2. **Database Operations**:
   - Drizzle ORM handles type-safe database queries
   - Fallback to in-memory storage during development
   - Automatic schema migrations via Drizzle Kit

## External Dependencies

### Database
- **Neon Database**: Serverless PostgreSQL provider
- **Connection**: Via `@neondatabase/serverless` driver

### UI Framework
- **Radix UI**: Headless UI primitives for accessibility
- **Lucide Icons**: Icon library for consistent iconography
- **Framer Motion**: Animation library for enhanced UX

### Development Tools
- **Replit Integration**: Vite plugins for Replit development environment
- **TypeScript**: Strict type checking enabled
- **ESBuild**: Fast bundling for production builds

## Deployment Strategy

### Build Process
1. Frontend builds via Vite to `dist/public`
2. Backend bundles via ESBuild to `dist/index.js`
3. Shared schemas and types remain accessible to both

### Environment Configuration
- `DATABASE_URL` required for PostgreSQL connection
- `NODE_ENV` for environment-specific behavior
- Vite handles static asset serving in development

### Production Deployment
- Static files served from `dist/public`
- Express server serves API and fallback to frontend
- Database migrations run via `npm run db:push`

## Changelog

```
Changelog:
- June 29, 2025. Initial setup
- June 29, 2025. Updated color scheme from blue to black/red theme
- June 29, 2025. Enhanced SpaceZ logo with rocket icon and improved typography
- June 29, 2025. Added PostgreSQL database with DatabaseStorage implementation
```

## User Preferences

```
Preferred communication style: Simple, everyday language.
```