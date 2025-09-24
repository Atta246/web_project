# Restaurant Website

A modern restaurant website built with Next.js, React, Tailwind CSS, and Express.js.

## Features

- **Homepage** with hero section, about section, featured menu items, and testimonials
- **Menu page** with filtering by categories and search functionality
- **Contact page** with contact form and information
- **Reservation page** with table booking functionality
- **Support chatbot** powered by OpenAI for instant customer assistance
- **Admin section**:
  - Admin login with Supabase authentication
  - Custom admin tables for fine-grained access control
  - Secure authentication with bcryptjs password hashing
  - Admin dashboard with statistics and quick actions
  - Reservation management
- **Dark/Light Mode** toggle functionality
- **Responsive Design** that works across devices

## Technology Stack

- **Frontend**: Next.js, React, Tailwind CSS
- **Backend**: Express.js, MongoDB, Supabase
- **Authentication**: JWT (JSON Web Tokens)
- **API**: REST API with Next.js API routes
- **AI**: OpenAI API for intelligent chatbot assistant

## Authentication System

The admin authentication system uses a secure Supabase table for storing admin credentials:

- **Admin Table**: Stores admin accounts with secure password hashing
- **Middleware**: Protects admin routes with token-based authentication
- **Auth Utilities**: Provides tools for verifying tokens and checking permissions


## Getting Started

First, run the development server:

```bash
npm run dev
# or
yarn dev
# or
pnpm dev
# or
bun dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

## Project Structure

- `src/app/*`: Next.js app router pages and components
- `src/app/api/*`: API routes for handling data
- `src/app/components/*`: Reusable UI components
- `src/app/context/*`: React context providers
- `src/app/services/*`: API service functions
- `src/app/lib/*`: Utility functions
- `server.js`: Express.js server configuration

## Setup Instructions

1. Clone the repository
2. Install dependencies:
   ```bash
   npm install
   ```

3. Run the development server:
   ```bash
   npm run dev
   ```



## Admin Access

- Default admin credentials:
  - Username: admin
  - Password: admin123

## Deployment

### Manual Deployment

1. Build the application:
   ```bash
   npm run build
   ```

2. Start the production server:
   ```bash
   npm start
   ```

### Deployment Platforms

This application can be deployed on:

- **Vercel**: Connect your GitHub repository and deploy automatically
- **Netlify**: Connect your GitHub repository and deploy automatically
- **AWS**: Deploy using Elastic Beanstalk or EC2
- **Heroku**: Deploy using the Node.js buildpack


## API Endpoints

### Menu Items
- `GET /api/menu`: Get all menu items
- `POST /api/menu`: Create a new menu item (admin only)
- `GET /api/menu/:id`: Get a specific menu item
- `PUT /api/menu/:id`: Update a menu item (admin only)
- `DELETE /api/menu/:id`: Delete a menu item (admin only)

### Reservations
- `POST /api/reservation`: Create a new reservation
- `GET /api/reservation`: Get all reservations (admin only)
- `GET /api/reservation/:id`: Get a specific reservation (admin only)
- `PUT /api/reservation/:id`: Update a reservation (admin only)
- `PATCH /api/reservation/:id/status`: Update reservation status (admin only)

### Authentication
- `POST /api/auth/login`: Login for admin access

### Contact
- `POST /api/contact`: Submit a contact form

