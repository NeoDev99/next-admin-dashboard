# Next Admin Dashboard

## Overview

This project is a Next.js admin dashboard application using TypeScript, Tailwind CSS, and various other libraries. It includes features such as authentication with NextAuth and GitHub, dynamic routing, and integration with Neon for the database.

## Folder Structure

    ``` bash
    📁 next-admin-dashboard
    |
    |_ 📁 app
    |  |_ 📁 (dashboard)
    |  |  |_ 📁 customers
    |  |  |  |_ 📄 page.tsx
    |  |  |_ 📄 page.tsx
    |  |  |_ 📄 layout.tsx
    |  |  |_ ...
    |  |_ 📁 api
    |  |  |_ 📁 seed
    |  |     |_ 📄 route.ts
    |  |_ 📄 layout.tsx
    |
    |_ 📁 components
    |  |_ 📁 ui
    |  |  |_ 📄 badge.tsx
    |  |  |_ 📄 button.tsx
    |  |  |_ 📄 input.tsx
    |  |  |_ 📄 sheet.tsx
    |  |  |_ 📄 table.tsx
    |  |  |_ ...
    |  |_ 📄 icons.tsx
    |
    |_ 📁 lib
    |  |_ 📄 db.ts
    |  |_ 📄 utils.ts
    |
    |_ 📁 styles
    |  |_ 📄 globals.css
    |
    |_ 📁 public
    |  |_ 📄 placeholder-user.jpg
    |  |_ 📄 placeholder.svg
    |
    |_ 📁 types
    |  |_ 📄 types.d.ts
    |
    |_ 📄 next.config.mjs
    |_ 📄 components.json
    |_ 📄 drizzle.config.ts
    |_ 📄 .env.local
    |_ 📄 .gitignore
    |_ 📄 package.json
    |_ 📄 tailwind.config.ts
    |_ 📄 tsconfig.json
    ```

## Setup and Installation

1. **Clone the Repository**

   ```bash
   git clone <repository-url>
   cd next-admin-dashboard
   ```

2. **Install Dependencies**

    ```bash
    npm install
    ```

3. **Configure Environment Variables**

    Create a .env.local file in the root of the project and add your environment variables:

    ```env
    AUTH_GITHUB_ID=<your-github-client-id>
    AUTH_GITHUB_SECRET=<your-github-client-secret>
    ```

4. **Setup Neon Database**

    Create a new Neon database and use the following SQL schema to set up your tables:

    ```sql
    CREATE TYPE status AS ENUM ('active', 'inactive', 'archived');

    CREATE TABLE products (
      id SERIAL PRIMARY KEY,
      image_url TEXT NOT NULL,
      name TEXT NOT NULL,
      status status NOT NULL,
      price NUMERIC(10, 2) NOT NULL,
      stock INTEGER NOT NULL,
      available_at TIMESTAMP NOT NULL
    );
    ```

5.  **Run Development Server**
   
    ```bash
    npm run dev
    ```

    This will start the development server at http://localhost:3000.


## Dependencies

- **Next.js**: The React framework used for server-side rendering and static site generation.
- **NextAuth**: Authentication library for Next.js, including GitHub authentication.
- **Tailwind CSS**: Utility-first CSS framework for styling.
- **Radix UI**: Component library providing accessibility and styling primitives.
- **Lucide React**: Icon library for React components.
- **Neon Database**: Serverless database for managing your data.

## Troubleshooting

- Image Configuration Error: Ensure you have added all required domains to the images.domains array in your `next.config.mjs`.

- Missing Environment Variables: Double-check your `.env.local` file for correct values.

- Database Errors: Ensure your Neon database schema is correctly set up and the connection string in   `.env.local` is accurate.

## License
This project is licensed under the MIT License. See the LICENSE file for details.
