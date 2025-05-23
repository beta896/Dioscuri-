Beta Dioscuri - Team Management Application
Overview
Beta Dioscuri is a team management application designed to facilitate task assignment, performance evaluation, and team collaboration. It's a full-stack application with a React frontend, Express backend, and PostgreSQL database using Drizzle ORM. The application provides features for user authentication, team creation, task management, performance tracking, and activity monitoring.

User Preferences
Preferred communication style: Simple, everyday language.

System Architecture
The application follows a client-server architecture with clearly separated frontend and backend components:

Frontend: React-based single-page application using React Query for data fetching, Tailwind CSS for styling, and shadcn/ui for UI components.

Backend: Express.js server providing RESTful API endpoints for data management, using Drizzle ORM for database operations.

Database: PostgreSQL (currently configured to use Drizzle ORM but will need to be set up in Replit).

Authentication: Session-based authentication using Passport.js with local strategy.

The application is designed to run as a monolithic application in development, with Vite handling the frontend bundling and hot module replacement.

Key Components
Frontend
React Components:

UI components from shadcn/ui library
Page components for different sections of the application
Context providers for authentication and global state
Data Management:

React Query for data fetching, caching, and state management
Custom hooks for shared functionality
Routing:

Wouter for lightweight client-side routing
Protected routes requiring authentication
Styling:

Tailwind CSS for utility-first styling
Custom theme with light/dark mode support
Backend
API Routes:

Authentication endpoints (login, logout, registration)
User management endpoints
Team management endpoints
Task management endpoints
Performance tracking endpoints
Activity logging endpoints
Data Access:

Drizzle ORM for type-safe database operations
Storage interface for database operations
Authentication:

Passport.js for authentication
Session-based auth with express-session
bcryptjs for password hashing
Database Schema
Users: Store user information including authentication details and role.
Teams: Manage team information including manager and invite code.
Tasks: Track assignments with status, priority, and deadlines.
Performance: Record performance metrics for team members.
Data Flow
Authentication Flow:

User submits login credentials
Server validates credentials and creates a session
Frontend stores user information in AuthContext
Protected routes check AuthContext
Task Management Flow:

Manager creates tasks assigned to team members
Tasks are stored in the database
Team members view and update task status
Activity is logged for status changes
Performance Tracking Flow:

Managers evaluate team member performance
Performance data is stored and updated
Dashboard displays performance metrics
External Dependencies
Frontend Dependencies
React and React DOM for UI rendering
React Query for data fetching and state management
Wouter for client-side routing
Tailwind CSS for styling
shadcn/ui components (based on Radix UI primitives)
React Hook Form for form handling
Zod for schema validation
Backend Dependencies
Express.js for server framework
Passport.js for authentication
bcryptjs for password hashing
Drizzle ORM for database operations
express-session for session management
Deployment Strategy
The application is configured for deployment in the Replit environment:

Development:

Run with npm run dev
Uses Vite's development server with HMR
Backend runs concurrently
Production:

Build step: npm run build
Frontend assets are built and placed in the dist/public directory
Backend serves static files and handles API requests
Run with npm run start
The deployment leverages Replit's autoscaling capabilities and is configured to expose port 5000 for HTTP traffic.

Getting Started
Ensure PostgreSQL is properly set up in your Replit environment.

Set the necessary environment variables:

DATABASE_URL: Connection string for PostgreSQL
SESSION_SECRET: Secret for session encryption
Install dependencies with npm install.

Run the database migrations with npm run db:push.

Start the development server with npm run dev.

Database Setup
The application uses Drizzle ORM to interact with PostgreSQL. The schema is defined in shared/schema.ts. Key tables include:

users: Stores user accounts and authentication details
teams: Manages team information
tasks: Tracks assignments and their status
performance: Records performance evaluations
Use the npm run db:push command to sync the schema with your database.