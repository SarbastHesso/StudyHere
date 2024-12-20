# App Architecture

The architecture of the **StudyHere** app is designed to ensure scalability, maintainability, and clear separation of concerns. It consists of frontend and backend components, with external services handling specific functionalities like OCR and summarization.

## Overview

StudyHere uses a **client-server architecture** with the following key components:

- **Frontend**: A React-based web app developed with **Vite**, responsible for rendering the user interface.
- **Backend**: Built with **Node.js** and **Express**, it handles API requests, user authentication, and data management.
- **APIs**: Facilitate communication between the frontend and backend.
- **External Services**: Used for advanced features such as **AI-based summarization** and **OCR** for text extraction from images.

## Frontend Architecture

### Core Technologies
- **React.js**: A JavaScript library for building user interfaces. The frontend is developed using React functional components and hooks for managing state and side effects.
- **Vite**: A build tool that provides fast hot module replacement (HMR) and efficient builds for frontend development.
- **CSS (TailwindCSS or Material-UI)**: TailwindCSS or Material-UI is used to style the components. The choice of styles depends on the design needs, with TailwindCSS offering a utility-first approach and Material-UI providing pre-built UI components.
- **React Router**: Manages navigation and routing within the app to different views or pages (e.g., home page, study page, flashcards page).

### Components Structure
- **Pages**: The app is divided into distinct pages based on user flows, such as the **HomePage**, **StudyPage**, **FlashcardsPage**, and **QuizzesPage**.
- **Reusable Components**: These include buttons, input fields, cards, lists, modals, and other UI elements used throughout the app.
- **Hooks**: Custom React hooks are created to handle various logic such as **data fetching**, **user authentication**, and managing global state.
- **Styles and Assets**:
  - **Styles**: The application uses **TailwindCSS** for utility-based styling or **Material-UI** for predefined component styling.
  - **Assets**: All images, icons, and fonts used by the frontend are stored in the **/assets** folder, making it easy to manage and reference them across different components.

## Backend Architecture

### Core Technologies
- **Node.js**: A JavaScript runtime environment that powers the backend, handling HTTP requests, authentication, and database interactions.
- **Express.js**: A minimal web framework for building RESTful APIs in Node.js. Express helps define routes, middleware, and handle requests from the frontend.
- **Database**:
  - **MongoDB** (Cloud): Used for storing user data, flashcards, quizzes, and study materials. MongoDB is chosen for cloud-based, scalable storage.
  - **SQLite** (Local): A lightweight database for offline data storage, enabling users to continue studying without an internet connection. Data is later synced with the cloud when the connection is restored.

### Services
- **OCR (Optical Character Recognition)**: Tesseract.js or an external OCR service is used to extract text from images uploaded by users.
- **Summarization**: The backend utilizes AI APIs like **OpenAI** or **Hugging Face** for summarizing large amounts of text into shorter, more digestible summaries.
- **Quiz Generation**: Based on the user’s flashcards and study materials, quizzes are generated to enhance learning.

### Endpoints
The backend exposes several **RESTful API endpoints** for interaction:
- **/api/auth/**: Manages user authentication (login, signup, JWT token handling).
- **/api/ocr/**: Processes images for OCR-based text extraction.
- **/api/flashcards/**: Provides CRUD operations for managing flashcards (create, read, update, delete).
- **/api/quizzes/**: Generates quizzes based on flashcards or study materials.
- **/api/summarization/**: Summarizes extracted text using AI-based services.

## Database Schema

### MongoDB (Cloud)
- **User**: Stores user details such as email, password, preferences, and study history.
- **Flashcards**: Stores flashcards created by users or generated from study material.
- **Quizzes**: Stores quizzes generated from flashcards or study materials.
- **Study Material**: Stores text or images that users upload for study purposes.

### SQLite (Local Storage)
- **Offline Sync**: When users are offline, study data like flashcards and materials are stored locally in SQLite. This data syncs with MongoDB once the user is back online.

## Third-Party Services

- **OCR Service**: **Tesseract.js** or an external OCR service extracts text from images.
- **Summarization Service**: AI-based services like **OpenAI** or **Hugging Face** generate text summaries to condense study materials.

## API Architecture

### Authentication
- **JWT (JSON Web Tokens)**: Used for user authentication. JWTs are issued on login and used for validating requests on protected endpoints.

### Routes & Endpoints
- **/api/auth/**: Handles user authentication operations such as login and signup.
- **/api/ocr/**: Handles text extraction from images via OCR.
- **/api/flashcards/**: Provides functionality for CRUD operations related to flashcards.
- **/api/quizzes/**: Allows users to generate quizzes based on flashcards and study material.
- **/api/summarization/**: Summarizes study material and text using AI-powered services.

## Communication Between Components

- **Frontend <-> Backend**: The frontend communicates with the backend via **RESTful APIs**. The frontend sends HTTP requests to backend endpoints, processes the data (e.g., OCR, summarization), and displays the results to users.
- **Backend <-> Third-Party Services**: The backend communicates with external services like **Tesseract.js** for OCR and **OpenAI** for summarization. These services process data and send back results to the backend, which are then delivered to the frontend.


