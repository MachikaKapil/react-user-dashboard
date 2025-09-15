# User Dashboard

## 1. Objective

The goal is to build a small “User Dashboard” application using React.js. This project will test your understanding of fundamental React concepts like components, hooks, state management, API calls, and routing.

## 2. Tech Stack

- **React:** For building the user interface with functional components and hooks.
- **React Router DOM:** For handling client-side navigation between pages.
- **Axios (or Fetch):** For making HTTP requests to a public API.
- **React Context:** For simple global state management.
- **Tailwind CSS:** For styling and creating a responsive design.

## 3. Getting Started: Step-by-Step Setup

Follow these instructions to set up your development environment.

### Prerequisites

Ensure you have [Node.js](https://nodejs.org/) (which includes npm) installed on your machine. You can check by running `node -v` and `npm -v` in your terminal.

### Step 3.1: Create Your React App

Open your terminal and run the following command to create a new React project named `user-dashboard`.

```
npx create-react-app user-dashboard

```

Navigate into your new project directory:

```
cd user-dashboard

```

### Step 3.2: Install Dependencies

We need to install a few libraries for routing, API calls, and styling.

```
npm install react-router-dom axios tailwindcss postcss autoprefixer

```

### Step 3.3: Initialize Tailwind CSS

Run these commands to create the necessary Tailwind configuration files (`tailwind.config.js` and `postcss.config.js`).

```
npx tailwindcss init -p

```

Next, configure your `tailwind.config.js` to tell Tailwind which files to scan for classes.

```
// tailwind.config.js
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: [
    "./src/**/*.{js,jsx,ts,tsx}",
  ],
  theme: {
    extend: {},
  },
  plugins: [],
}

```

Finally, add the Tailwind directives to your main CSS file, `src/index.css`. Replace the existing content with this:

```
/* src/index.css */
@tailwind base;
@tailwind components;
@tailwind utilities;

```

Your project is now set up! You can start the development server by running:

```
npm start

```

## 4. Implementation Guide

Let's build the application feature by feature.

### Step 4.1: Project Structure

A clean folder structure helps keep your code organized. Create the following folders inside your `src` directory:

- `src/components`: For reusable UI components (e.g., `UserCard.jsx`, `Header.jsx`).
- `src/pages`: For top-level page components (e.g., `DashboardPage.jsx`, `UserDetailsPage.jsx`).
- `src/context`: For our React Context files (e.g., `UserContext.jsx`).
- `src/api`: For API-related logic (e.g., `userService.js`).

### Step 4.2: Setting up Global State (React Context)

We'll use the Context API to fetch the user data once and make it available throughout the entire app.

**1. Create the API Service (`src/api/userService.js`):**

This file will handle the API call to fetch users. We'll use the free [JSONPlaceholder API](https://www.google.com/search?q=https://jsonplaceholder.typicode.com/users).

**2. Create the User Context (`src/context/UserContext.jsx`):**

This is where we'll define our global state.

**3. Provide the Context to Your App (`src/index.js`):**

Wrap your `<App />` component with the `UserProvider` so that all components inside `App` can access the user data.

### Step 4.3: Setting up Routing

Now, let's define the pages and the routes for our application in `src/App.js`.

### Step 4.4: Building the Dashboard Page

This page will display the list of users, a search bar, and a form to add new users. We will assemble it from smaller, reusable components. For a complete, single-file example combining all components, see the `App.jsx` file provided alongside this guide.

### Step 4.5: Building the User Details Page

This page shows all information for a single, selected user. It will fetch the user ID from the URL.

## 5. Styling and Responsive Design

Tailwind CSS makes responsiveness easy. Use its utility classes:

- **Flexbox/Grid:** Use `flex`, `grid`, `grid-cols-1`, `md:grid-cols-2`, `lg:grid-cols-3` for layouts that adapt to screen size.
- **Spacing:** Use `p-4`, `m-2` for padding and margin.
- **Breakpoints:** Prefixes like `sm:`, `md:`, `lg:` apply styles only on certain screen sizes (e.g., `w-full md:w-1/2`).
