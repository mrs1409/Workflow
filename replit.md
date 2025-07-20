# Overview

This is a full-stack TypeScript application for intelligently organizing Gmail and Slack messages using AI categorization. Users authenticate via Replit Auth, connect their Gmail and Slack accounts through OAuth, and receive AI-powered summaries and action items organized into Urgent, FYI, and Ignored categories. The application features a glassmorphism dark theme design with smooth animations and a modern productivity-focused interface.

# User Preferences

Preferred communication style: Simple, everyday language.

# System Architecture

The application follows a monorepo structure with clear separation between client and server code:

- **Frontend**: React with TypeScript, using Vite for development and building
- **Backend**: Express.js with TypeScript running on Node.js
- **Database**: PostgreSQL with Drizzle ORM for database operations
- **Authentication**: Replit Auth integration with session management
- **Styling**: Tailwind CSS with Shadcn/ui components and glassmorphism design
- **State Management**: TanStack Query for server state management

# Key Components

## Frontend Architecture
- **React Router**: Using Wouter for lightweight routing
- **UI Components**: Shadcn/ui component library with Radix UI primitives
- **Animations**: Framer Motion for smooth interactions and micro-animations
- **Form Handling**: React Hook Form with Zod validation
- **Dark Mode**: Default dark theme with glassmorphism aesthetic

## Backend Architecture
- **API Design**: RESTful endpoints under `/api` prefix
- **Authentication**: Passport.js with OpenID Connect (Replit Auth)
- **Session Management**: Express sessions stored in PostgreSQL
- **Database Access**: Drizzle ORM with connection pooling via Neon serverless

## Database Schema
The application uses four main tables:
- `users`: User profiles with onboarding status and connection flags
- `sessions`: Session storage for authentication (required by Replit Auth)  
- `workItems`: AI-processed messages with classification, summaries, action items, urgency scores
- `connectedAccounts`: OAuth tokens for Gmail and Slack integrations

# Data Flow

1. **Authentication Flow**: Users authenticate via Replit Auth, sessions stored in database
2. **Onboarding Flow**: New users connect Gmail/Slack accounts via OAuth
3. **Data Processing**: Messages fetched from connected services, processed by AI for categorization and summarization
4. **Work Item Management**: AI-generated work items displayed in dashboard with quick actions
5. **Real-time Updates**: Client-side optimistic updates with TanStack Query

# External Dependencies

## Core Technologies
- **Database**: PostgreSQL (via Neon serverless driver)
- **Authentication**: Replit Auth with OpenID Connect
- **UI Framework**: React with TypeScript
- **Styling**: Tailwind CSS + Shadcn/ui components
- **Animation**: Framer Motion
- **Forms**: React Hook Form + Zod validation
- **HTTP Client**: Native fetch with TanStack Query

## Development Tools
- **Build Tool**: Vite for frontend, esbuild for backend
- **Database Migrations**: Drizzle Kit
- **Type Safety**: TypeScript throughout with shared schemas
- **Development**: Hot reload with Vite dev server

# Deployment Strategy

The application is configured for deployment on Replit with:
- **Build Process**: Vite builds frontend to `dist/public`, esbuild bundles server to `dist/index.js`
- **Environment**: Production mode uses built assets, development uses Vite dev server
- **Database**: Expects `DATABASE_URL` environment variable for PostgreSQL connection
- **Authentication**: Requires Replit-specific environment variables for OAuth flow
- **Static Assets**: Frontend served from Express in production, Vite dev server in development

The architecture supports both development and production environments with appropriate tooling and optimizations for each context.

# Recent Changes (July 19, 2025)

- **Removed Mock Data**: Eliminated all dummy/placeholder work items from dashboard
- **Added Onboarding Flow**: Created dedicated onboarding page for connecting Gmail and Slack
- **Updated Landing Page**: Added email input for user registration before OAuth
- **Enhanced Database Schema**: Added user onboarding flags and connection status tracking
- **Implemented OAuth Placeholders**: Created backend endpoints for Gmail and Slack connection flow
- **Updated Routing Logic**: App now redirects users to onboarding if no connected accounts
- **Improved Empty States**: Dashboard shows connection prompts when no work items exist