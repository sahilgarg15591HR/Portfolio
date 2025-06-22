# Sahil Garg Portfolio - System Architecture Documentation

## Overview

This is a full-stack portfolio website for Sahil Garg, a Senior HR Professional and XLRI Alumni. The application is built as a modern web application with a React frontend and Express.js backend, featuring a contact form, CV download functionality, and professional portfolio display.

## System Architecture

### Frontend Architecture
- **Framework**: React 18 with TypeScript
- **Build Tool**: Vite for fast development and optimized production builds
- **UI Library**: shadcn/ui components built on Radix UI primitives
- **Styling**: Tailwind CSS with custom design system
- **State Management**: TanStack Query (React Query) for server state management
- **Routing**: Wouter for lightweight client-side routing
- **Form Handling**: React Hook Form with Zod validation

### Backend Architecture
- **Runtime**: Node.js with Express.js framework
- **Language**: TypeScript with ES modules
- **Database**: PostgreSQL with Drizzle ORM
- **Database Provider**: Neon Database (serverless PostgreSQL)
- **Session Management**: Express sessions with PostgreSQL store
- **Development**: Hot reload with tsx for TypeScript execution

### Build and Development
- **Monorepo Structure**: Client and server code in unified workspace
- **Development**: Concurrent client and server development with Vite proxy
- **Production Build**: Client builds to static files, server bundles with esbuild
- **Path Aliases**: Configured for clean imports (@/, @shared/, @assets/)

## Key Components

### Database Schema (`shared/schema.ts`)
- **Contacts Table**: Stores contact form submissions with name, email, phone, message, and timestamp
- **Users Table**: Basic user authentication structure (username/password)
- **Validation**: Zod schemas for type-safe data validation and API contracts

### API Layer (`server/routes.ts`)
- **Contact Management**: POST /api/contacts for form submissions, GET /api/contacts for retrieval
- **File Download**: GET /api/download-cv for resume download functionality
- **Error Handling**: Centralized error handling with proper HTTP status codes
- **Request Logging**: Detailed API request logging with response times and payloads

### Storage Layer (`server/storage.ts`)
- **Interface-Driven Design**: IStorage interface for flexible data access patterns
- **Memory Storage**: Development-friendly in-memory storage implementation
- **Database Ready**: Architecture supports easy migration to PostgreSQL production storage

### UI Components
- **Design System**: Comprehensive shadcn/ui component library
- **Responsive Design**: Mobile-first approach with Tailwind CSS
- **Accessibility**: ARIA-compliant components with keyboard navigation
- **Portfolio Sections**: Navigation, Hero, Experience, Skills, Education, Contact

## Data Flow

1. **User Interaction**: User fills out contact form or requests CV download
2. **Client Validation**: Form data validated using Zod schemas on client-side
3. **API Request**: TanStack Query manages server communication with optimistic updates
4. **Server Processing**: Express routes handle business logic and data persistence
5. **Database Operations**: Drizzle ORM manages PostgreSQL interactions
6. **Response Handling**: Structured JSON responses with error handling
7. **UI Updates**: React Query updates UI state and shows user feedback via toast notifications

## External Dependencies

### Database
- **Neon Database**: Serverless PostgreSQL for production
- **Drizzle ORM**: Type-safe database operations with schema migrations
- **Connection**: Environment-based DATABASE_URL configuration

### UI and Styling
- **Radix UI**: Accessible component primitives
- **Tailwind CSS**: Utility-first CSS framework
- **Lucide Icons**: Consistent icon library
- **Google Fonts**: Inter font family for typography

### Development Tools
- **TypeScript**: Static type checking across full stack
- **ESLint/Prettier**: Code quality and formatting (implied by project structure)
- **Vite Plugins**: Runtime error overlay, cartographer for Replit integration

## Deployment Strategy

### Replit Configuration
- **Runtime**: Node.js 20 with PostgreSQL 16 module
- **Development**: npm run dev starts concurrent client/server development
- **Production Build**: npm run build creates optimized client bundle and server executable
- **Deployment**: Autoscale deployment target with port 5000 to 80 mapping

### Environment Setup
- **Database**: Requires DATABASE_URL environment variable for PostgreSQL connection
- **Build Process**: Client builds to dist/public, server builds to dist/index.js
- **Static Files**: Express serves built client files in production

### Performance Considerations
- **Code Splitting**: Vite automatically splits code for optimal loading
- **Asset Optimization**: Static assets served efficiently in production
- **Database Connection**: Serverless PostgreSQL scales automatically
- **Caching**: TanStack Query provides intelligent client-side caching

## Recent Changes

- **June 22, 2025**: Enhanced UI with modern design system
  - Implemented gradient backgrounds and glassmorphism effects
  - Added hover animations and floating elements
  - Redesigned experience section from timeline to compact 2-column grid
  - Improved visual hierarchy with purple/blue gradient color scheme
  - Added pulse animations and glass navigation bar

## Changelog

```
Changelog:
- June 22, 2025. Initial setup and modern UI redesign
```

## User Preferences

```
Preferred communication style: Simple, everyday language.
```