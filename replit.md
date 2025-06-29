# replit.md

## Overview

My Moon is a nighttime-only anonymous emotional sharing platform designed to create a safe space for users to express their thoughts and feelings between 10 PM and 4 AM. The application combines emotional support with AI assistance, fostering genuine connections through anonymity while maintaining mental health awareness.

## System Architecture

### Frontend Architecture
- **Framework**: React with TypeScript using Vite as the build tool
- **UI Library**: shadcn/ui components built on Radix UI primitives
- **Styling**: Tailwind CSS with custom moon-themed variables and dark mode support
- **State Management**: TanStack Query for server state management
- **Routing**: Wouter for lightweight client-side routing
- **Real-time Communication**: WebSocket integration for live updates

### Backend Architecture
- **Runtime**: Node.js with Express.js server
- **Language**: TypeScript with ES modules
- **Database**: PostgreSQL with Drizzle ORM for type-safe database operations
- **Database Provider**: Neon Database (serverless PostgreSQL)
- **Session Management**: Anonymous session tracking using generated session IDs
- **Real-time**: WebSocket server for live post updates and notifications

### Authentication Strategy
- **Anonymous-first**: No traditional user accounts required
- **Session-based**: Temporary session IDs for interaction tracking
- **Privacy-focused**: All posts and interactions are anonymous by default

## Key Components

### Time-based Access Control
- Application only accessible between 10 PM - 4 AM local time
- Client-side and server-side time validation
- Graceful UI states for non-accessible hours

### Post System
- **Thought Posts**: General emotional sharing with mood tags (happy, sad, angry)
- **Question Posts**: Q&A format for seeking advice
- **Voice Notes**: Optional audio attachments (once per day limit)
- **AI Integration**: Automatic MoonBot replies when posts receive no human responses

### Interaction Features
- **Moon-themed Reactions**: Full Moon, Waning Crescent, New Moon emojis
- **Anonymous Comments**: Threaded discussions without identity
- **Real-time Updates**: Live post feeds and reaction updates

### Mental Health Features
- **MoonShield**: AI-powered content analysis for distress detection
- **Resource Integration**: Automatic mental health resource suggestions
- **Empathetic AI**: Compassionate automated responses from MoonBot

### UI/UX Design
- **Dark Theme**: Night-optimized design with cosmic purple and moon white colors
- **Ambient Features**: Optional background sounds (rain, lo-fi music)
- **Floating Elements**: Animated stars and moon imagery
- **Glass Morphism**: Modern glass card effects throughout the interface

## Data Flow

1. **User Access**: Time validation → Anonymous session creation → App access
2. **Content Creation**: Post composition → Mood/type selection → Database storage → WebSocket broadcast
3. **Real-time Updates**: Database changes → WebSocket notifications → Client state updates
4. **AI Processing**: New posts → OpenAI analysis → MoonBot response generation → Automatic posting
5. **Mental Health Monitoring**: Content analysis → Risk assessment → Resource recommendations

## External Dependencies

### Core Libraries
- **Database**: Drizzle ORM with Neon Database serverless PostgreSQL
- **AI Services**: OpenAI GPT-4 for MoonBot responses and mental health analysis
- **UI Components**: Radix UI primitives with shadcn/ui component library
- **Styling**: Tailwind CSS with PostCSS for processing
- **Real-time**: Native WebSocket implementation

### Development Tools
- **Build Tool**: Vite with React plugin
- **Type Safety**: TypeScript with strict configuration
- **Code Quality**: ESLint and Prettier (implied by project structure)
- **Development Environment**: Replit-specific plugins and error handling

## Deployment Strategy

### Production Build
- **Frontend**: Vite build process generating static assets
- **Backend**: esbuild compilation to ES modules for Node.js
- **Database**: Drizzle migrations for schema management
- **Environment**: Environment variable configuration for database and API keys

### Development Environment
- **Hot Reload**: Vite dev server with HMR
- **Database**: Development database connection via environment variables
- **API Integration**: Local development with proxy configuration
- **Real-time Testing**: WebSocket connection in development mode

### Database Schema
- **Posts Table**: Content, mood, type, timestamps, voice note URLs
- **Comments Table**: Post relationships, anonymous content
- **Reactions Table**: Session-based tracking, reaction types
- **AI Replies Table**: Automated response storage and metadata

## User Preferences

Preferred communication style: Simple, everyday language.

## Changelog

Changelog:
- June 29, 2025. Initial setup