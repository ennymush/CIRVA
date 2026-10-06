# CIRVA (Circle Value)

CIRVA is a digital financial operating system for African community finance. The platform digitizes traditional savings, contribution, support, lending, cooperative, and investment structures (Ajo, Esusu, Isida, Collaborative, Cooperative) while maintaining transparency, trust, accountability, and automation.

## Project Structure

This monorepo contains:
- `/backend`: NestJS backend API with Prisma ORM, JWT, and Postgres/Redis database support. Includes business logic for Ajo, DEHO swapping, Esusu loans, Isida pools, Collaborative investments, Cooperative systems, and an AI scoring simulation.
- `/frontend`: Next.js frontend with Tailwind CSS and Framer Motion. Provides interactive dashboards, wallet ledger trackers, swap request interfaces, loan calendars, investment panels, and an admin analytics interface.

---

## Setup & Running Locally

You can run the entire ecosystem locally using **Docker Compose** or run the backend and frontend services individually.

### Method 1: Using Docker Compose (Recommended)

1. Make sure you have Docker installed and running.
2. Run the following command in the project root:
   ```bash
   docker-compose up --build
   ```
3. The services will be available at:
   - Frontend: `http://localhost:3000`
   - Backend: `http://localhost:3001`

### Method 2: Running Services Individually (Standalone Mode)

#### 1. Backend Setup
1. Navigate to `/backend`:
   ```bash
   cd backend
   ```
2. Install dependencies:
   ```bash
   npm install
   ```
3. Set up your `.env` file (a default `.env` will be auto-generated with mock database fallbacks).
4. Run in development mode:
   ```bash
   npm run start:dev
   ```
   *Note: If PostgreSQL and Redis are not running locally, the NestJS API will automatically fall back to an in-memory data store, allowing full API testing without external dependencies.*

#### 2. Frontend Setup
1. Navigate to `/frontend`:
   ```bash
   cd frontend
   ```
2. Install dependencies:
   ```bash
   npm install
   ```
3. Run the development server:
   ```bash
   npm run dev
   ```
4. Access the portal at `http://localhost:3000`.

---

## Technical Highlights

- **DEHO (Dynamic Exchange Hold Option)**: Facilitates instant position swaps between circle members with multi-tier approvals.
- **Double-Entry Wallet Accounting**: Full ledger records are kept for all user and group transactions.
- **AI Risk & Fraud Scoring**: Real-time evaluation of user risk indices based on participation activity and KYC status.
- **Adjustable Revenue Engine**: Platform fees, withdrawal parameters, and subscription systems can be updated dynamically via the Admin Panel.
