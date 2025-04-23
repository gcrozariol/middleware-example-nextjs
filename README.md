# Middleware Example with Next.js

This project demonstrates how to handle public and private routes in a Next.js application using middleware. Below are the instructions to set up, run, and test the project.

## Installation

1. Clone the repository:

  ```bash
  git clone https://github.com/gcrozariol/middleware-example-nextjs.git
  cd middleware-example-nextjs
  ```

2. Install the dependencies:

  ```bash
  npm install
  ```

## Running the Project

To start the development server, run:

```bash
npm run dev
```

The application will be available at `http://localhost:3000`.

## Route Behaviour

### Public and Private Routes

- **Dashboard (`/dashboard`)**:  
  - If there is no token in the cookies, the user will be redirected to the sign-in page (`/sign-in`).
  - If the user is authenticated (has a valid token), they can access the dashboard.

- **Sign-In (`/sign-in`)**:  
  - If the user is not authenticated, they can access the sign-in page.
  - If the user is authenticated (has a valid token), they will be redirected to the dashboard.

- **Pricing (`/pricing`)**:  
  - This route is accessible to both authenticated and unauthenticated users.

## Testing the Routes

### Without a Token

1. Clear your browser cookies or ensure no token is present.
2. Try accessing `/dashboard`. You should be redirected to `/sign-in`.
3. Access `/pricing`. You should be able to view the page.

### With a Token

1. Open your browser's developer tools and navigate to the "Application" tab.
2. Under "Storage," locate "Cookies" and select the domain for the application.
3. Add a new cookie with the key `token` and set its value to any string.
4. Refresh the page and try accessing `/dashboard`. You should be able to view the page.
5. Try accessing `/sign-in`. You should be redirected to `/dashboard`.
6. Access `/pricing`. You should still be able to view the page.
