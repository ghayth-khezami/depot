# DEPOT Management System

Full-stack application for DEPOT management with NestJS backend and React frontend.

## Project Structure

```
depot/
├── client/          # React frontend (Vite + TypeScript + RTK Query)
├── server/          # NestJS backend (Prisma + PostgreSQL)
└── README.md        # This file
```

## Features

### Backend (Server)
- **NestJS** with Prisma ORM
- **PostgreSQL** database
- **Swagger** API documentation
- Full CRUD operations for Users, Clients, CoClients, Categories, and Products
- Pagination, search, and filtering on all endpoints

### Frontend (Client)
- **React** with TypeScript
- **Vite** for fast development
- **RTK Query** for API state management
- **Tailwind CSS** for styling
- Reusable table component with search, filters, and pagination
- Modal forms for add/update operations

## Quick Start

### Prerequisites

- Node.js (v18 or higher)
- pnpm
- PostgreSQL database

### Backend Setup

1. Navigate to the server directory:
```bash
cd server
```

2. Install dependencies:
```bash
pnpm install
```

3. Create a `.env` file in the server directory:
```env
DATABASE_URL="postgresql://user:password@localhost:5432/DEPOT?schema=public"
```

4. Create the `DEPOT` database in pgAdmin

5. Generate Prisma Client and run migrations:
```bash
pnpm prisma:generate
pnpm prisma:migrate
```

6. Start the backend server:
```bash
pnpm start:dev
```

The API will be available at `http://localhost:3000`
Swagger documentation at `http://localhost:3000/api`

### Frontend Setup

1. Navigate to the client directory:
```bash
cd client
```

2. Install dependencies:
```bash
pnpm install
```

3. Start the development server:
```bash
pnpm dev
```

The frontend will be available at `http://localhost:5173`

## API Endpoints

### Users
- `GET /users` - Get all users (paginated, searchable)
- `GET /users/:id` - Get user by ID
- `PATCH /users/:id` - Update user
- `DELETE /users/:id` - Delete user

### Clients
- `GET /clients` - Get all clients (paginated, searchable)
- `GET /clients/:id` - Get client by ID
- `POST /clients` - Create client
- `DELETE /clients/:id` - Delete client

### CoClients
- `GET /co-clients` - Get all co-clients (paginated, searchable)
- `GET /co-clients/:id` - Get co-client by ID
- `POST /co-clients` - Create co-client
- `DELETE /co-clients/:id` - Delete co-client

### Categories
- `GET /categories` - Get all categories (paginated, searchable)
- `GET /categories/:id` - Get category by ID
- `POST /categories` - Create category
- `PATCH /categories/:id` - Update category
- `DELETE /categories/:id` - Delete category

### Products
- `GET /products` - Get all products (paginated, searchable, filterable)
- `GET /products/:id` - Get product by ID
- `PATCH /products/:id` - Update product
- `DELETE /products/:id` - Delete product

## Database Schema

The application includes the following tables:
- `users` - User authentication and credentials
- `clients` - Client information
- `co_clients` - Co-client information with RIB
- `categories` - Product categories
- `products` - Product information
- `product_photos` - Product photos (one-to-many with products)
- `commands` - Order/command information
- `command_details` - Command details linking commands, products, clients, and co-clients

## Development

### Backend Development
```bash
cd server
pnpm start:dev
```

### Frontend Development
```bash
cd client
pnpm dev
```

### Building for Production

**Backend:**
```bash
cd server
pnpm build
pnpm start:prod
```

**Frontend:**
```bash
cd client
pnpm build
```

## License

MIT
