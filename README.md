# Restaurant Website

This project is a restaurant web application built with Next.js, React, Tailwind CSS, and a small Express/MongoDB server for legacy API support. It includes a public customer-facing site, an admin area, reusable UI components, and supporting scripts for database and account setup.

## What The App Does

The application provides a full restaurant experience:

- A marketing homepage with hero content, featured items, and supporting sections
- A browsable menu with category filtering and search
- Reservation and contact flows for customers
- A support chatbot powered by OpenAI
- An admin dashboard for managing menu items and reservations
- Authentication and route protection for admin pages

## Tech Stack

- **Frontend**: Next.js, React, Tailwind CSS
- **State and UI helpers**: React Context, Framer Motion, Lucide icons, Chart.js
- **Data and auth**: Supabase, bcryptjs, jsonwebtoken
- **Server support**: Express.js, MongoDB via Mongoose
- **AI**: OpenAI and Azure AI inference packages
- **Testing**: Jest, React Testing Library, Supertest

## Project Structure

The codebase is organized by feature and responsibility:

- `src/app/page.js`: Public homepage
- `src/app/menu/page.js`: Menu browsing and filtering
- `src/app/contact/page.js`: Contact form and details
- `src/app/reservation/page.js`: Reservation flow
- `src/app/support/page.js`: Support/chat experience
- `src/app/checkout/page.js`: Checkout flow
- `src/app/admin/*`: Admin layout, login, dashboard, reports, menu, and reservation screens
- `src/app/api/*`: Next.js API routes for menu, reservations, auth, chat, and validation endpoints
- `src/app/components/*`: Reusable UI components such as navbar, footer, cart sidebar, auth modal, and chat message
- `src/app/context/*`: React context providers for auth, cart, customer auth, and theme state
- `src/app/lib/*`: Shared utilities for auth, Supabase, formatting, AI integration, and middleware helpers
- `src/app/services/*`: Higher-level service wrappers used by the app UI
- `src/app/middleware/*`: Admin middleware helpers
- `src/app/utils/*`: General-purpose utility functions
- `setup/*`: Database, admin, and verification scripts used during local setup
- `__tests__/*`: Unit and integration-style tests for API routes, components, pages, and utilities
- `server.js`: Standalone Express server with MongoDB-backed routes

## How The Pieces Fit Together

The public UI lives in the Next.js app router under `src/app`. UI pages call shared service modules in `src/app/services` and `src/app/lib`, which wrap Supabase access, auth checks, formatting, and chatbot helpers.

The admin area uses the same app router structure, but it is protected by middleware and authentication helpers. Supporting scripts in `setup/` help create admin accounts, initialize database tables, and verify local configuration.

The repository also includes `server.js` for Express-based API support. That file uses MongoDB models for menu items, reservations, and admin logins, which makes the project a hybrid setup rather than a single-server-only Next.js app.

## Getting Started

Install dependencies and start the development server:

```bash
npm install
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser.

## Available Scripts

- `npm run dev`: Start the Next.js development server
- `npm run build`: Build the application for production
- `npm start`: Start the production server
- `npm run lint`: Run lint checks
- `npm test`: Run the test suite
- `npm run test:api`: Run API-focused tests
- `npm run test:components`: Run component-focused tests

## Environment Notes

The app expects environment variables for Supabase, OpenAI or Azure AI integration, and any MongoDB connection used by `server.js`. Check the setup scripts and the source files in `src/app/lib` for the exact values required by each feature.

## Admin Access

The setup scripts can create a default admin account for local development. If you use the bundled scripts, the common default credentials are:

- Username: `admin`
- Password: `admin123`

## Deployment

The Next.js app can be deployed on common platforms such as Vercel or Netlify. If you also need the Express backend, deploy `server.js` separately in an environment that supports a Node.js process and MongoDB connectivity.

