# Frontend Development

This document outlines the structure, tools, and best practices for developing the frontend of the StudyHere app.

---

## Overview

The frontend of StudyHere is a React-based web application powered by Vite. It is designed to provide a seamless and intuitive user experience, leveraging modern UI and state management libraries.

---

## Core Technologies

The key technologies used in the frontend include:

- **React.js**: A JavaScript library for building user interfaces.
- **Vite**: A modern development environment with fast module replacement.
- **CSS (Tailwind or Material-UI)**: For styling and design consistency.
- **React Router**: For managing app routes and navigation.
- **Axios**: For handling API calls to the backend.

---

## Folder Structure

The recommended folder structure for the frontend is as follows:

```
frontend/
├── public/          # Static assets (e.g., images, icons, fonts)
├── src/
│   ├── assets/      # Images, logos, and other media
│   ├── components/  # Reusable React components
│   ├── context/     # React Contexts for global state management
│   ├── hooks/       # Custom hooks for logic (e.g., API fetching)
│   ├── pages/       # Full-page components (e.g., Home, Flashcards, Quiz)
│   ├── services/    # API service functions
│   ├── styles/      # Global and reusable styles (e.g., CSS or SCSS files)
│   ├── App.tsx      # Main app component
│   ├── main.tsx     # Entry point of the React app
├── package.json     # Project dependencies and scripts
```

---

## Key Pages

### Home Page
- **Purpose**: Acts as the main dashboard, providing access to key features like text extraction, flashcards, and quizzes.
- **Components**: Includes navigation bar, feature cards, and user summaries.

### Flashcards Page
- **Purpose**: Allows users to view, create, and manage flashcards.
- **Components**: Flashcard grid, flashcard editor, and quiz generator.

### Quiz Page
- **Purpose**: Presents quizzes generated from study material or flashcards.
- **Components**: Question display, timer, and results page.

---

## State Management

- **React State**: Used for managing local UI state.
- **Context API**: Used for global state management, including user authentication and app settings.
- **Custom Hooks**: Logic like API calls and data fetching are handled using custom hooks for better reusability.

---

## Styling

- **Global Styles**: Defined in a central CSS or SCSS file for consistency.
- **Component-Level Styles**: Scoped styles for individual components using CSS Modules or styled-components.

---

## Development Best Practices

- Use meaningful component names and file structures.
- Keep components small and focused (one responsibility per component).
- Write reusable custom hooks for complex logic.
- Test API calls and error handling thoroughly.
- Follow a consistent coding style (e.g., Prettier for formatting).

---

## Running the Frontend Locally

To run the frontend development server, follow these steps:

1. Navigate to the `frontend` folder:
   ```bash
   cd frontend
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Start the development server:
   ```bash
   npm run dev
   ```

4. Access the app in your browser at [http://localhost:3000](http://localhost:3000).

---

## Troubleshooting

- **Issues with dependencies**: Run `npm install` to ensure all dependencies are installed.
- **Build errors**: Check the console for detailed error messages.
- **Styling issues**: Verify that Tailwind or Material-UI is correctly set up in the project.

For more details, refer to the [App Architecture](./architecture.md) document.