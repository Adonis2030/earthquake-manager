# Earthquake Manager

This is a project containing both the **frontend** and **backend** for the Earthquake Manager application. The frontend is built with **Next.js**, **Apollo Client**, and **Tailwind CSS**, while the backend is a **Node.js** GraphQL API built using **Apollo Server**, **Express**, and **TypeScript**. The app manages earthquake data, allowing for querying, listing, and manipulating data.

## Features

The **Earthquake Manager** application provides a complete solution for managing earthquake data, both from the frontend and backend. Below are the key features of the application:

### Frontend Features

1. **Earthquake Listing**:

   - The application displays a list of recorded earthquakes, showing essential details such as location, magnitude, and date.
   - Earthquakes can be sorted or filtered based on these properties to make it easier to find specific data.

2. **Create, Update, and Delete Earthquakes**:

   - Users can add new earthquake records by entering location, magnitude, and date. These inputs are validated before submission to ensure data integrity.
   - Existing earthquake records can be updated with new information.
   - Earthquakes can be deleted if no longer relevant, with confirmation prompts to prevent accidental deletions.

3. **Responsive UI**:

   - The UI is built with **Tailwind CSS**, ensuring a clean, modern, and responsive design that works across different devices and screen sizes.

4. **GraphQL Integration**:

   - The frontend communicates with the backend using **GraphQL** for efficient data fetching and state management. This allows the UI to dynamically display the latest earthquake data without reloading the page.

5. **Real-Time Updates** (Optional):

   - Through GraphQL subscriptions or polling, users can be notified of new earthquakes or changes in existing records, providing real-time data updates.

6. **TypeScript Support**:
   - The frontend uses **TypeScript** to ensure strong typing, reducing the likelihood of runtime errors and improving code quality and maintainability.

### Backend Features

1. **GraphQL API**:

   - The backend uses **Apollo Server** with **GraphQL** to provide a flexible and efficient way to query and mutate earthquake data.
   - Queries allow for fetching all earthquake records or a specific earthquake by ID.
   - Mutations support creating, updating, and deleting earthquake records.

2. **CSV Data Import**:

   - The backend can parse a CSV file to load initial earthquake data into the system, making it easy to populate the database with existing records or bulk data from external sources.

3. **Node.js with Express**:

   - The server is built with **Node.js** and **Express**, making it lightweight and scalable for handling API requests and managing data.

4. **Data Validation**:

   - All mutations (create, update, delete) are validated on the backend to ensure that only properly formatted and valid data is stored in the system.

5. **UUID for Earthquake IDs**:

   - Each earthquake is assigned a unique identifier (UUID), ensuring that the records are managed efficiently, especially when dealing with large datasets.

6. **TypeScript Support**:

   - The backend uses **TypeScript**, ensuring that data types are strictly enforced, making the codebase more robust and maintainable.

### Additional Features

- **Cross-Origin Resource Sharing (CORS)**:

  - The backend supports **CORS**, allowing the frontend to make API requests from a different domain or port, enabling smooth integration between the frontend and backend.

- **Development Mode with Live Reloading**:

  - Both the frontend and backend support development modes with live reloading, making the development process smoother. Any changes to the code automatically trigger a reload, reducing the need for manual restarts.

## Getting Started

### Prerequisites

- **Node.js** (v18.x or higher)
- **npm** or **yarn** installed

### Installation

1. **Clone the repository**:

   ```bash
   git clone git@github.com:Adonis2030/earthquake-manager.git
   cd earthquake-manager
   ```

2. **Install dependencies for frontend**:

   ```bash
   cd earthquake-manager-frontend
   npm install
   ```

3. **Install dependencies for backend**:

   ```bash
   cd earthquake-manager-backend
   npm install
   ```

4. **Running the Frontend**:
   To run the forntend development server, navigate to the `frontend` directory and run:

```bash
npm run dev
```

The frontend will be available at `http://localhost:3000`.

5. **Running the Backend**:
   To run the backend, navigate to the `backend` directory and start the server:

```bash
npm run start
```

6. **Testing GraphQL Queries and Mutations**:
   Access the Apollo Server playground at `http://localhost:4000/graphql` and try out the following sample queries and mutations:

- **Get all earthquake**:

```graphql
query {
  earthquakes {
    id
    location
    magnitude
    date
  }
}
```

- **Create a new earthquake**:

```graphql
mutation {
  createEarthquake(input: { location: "New Location", magnitude: 6.5, date: "2024-09-26" }) {
    id
    location
    magnitude
    date
  }
}
```

### Key Technologies

1. **Frontend**

- Next.js: Server-side rendering and static site generation framework for React.
- Apollo Client: State management and GraphQL queries.
- Material-UI: UI components for responsive design.
- Tailwind CSS: Utility-first CSS framework for styling.
- TypeScript: Type safety and code quality.

2. **Backend**

- Apollo Server: GraphQL server for building the API.
- Express: Web framework for Node.js.
- TypeScript: Type safety and code quality.
- CSV Parser: For loading earthquake data from a CSV file.
- UUID: For generating unique earthquake IDs.

### Scripts

1. **Frontend**

`dev`: Starts the development server.
`build`: Builds the app for production.
`start`: Runs the production build.
`lint`: Lints the code.

2. **Backend**

`start`: Starts the GraphQL API server.
`compile`: Compiles the TypeScript files.
`dev`: Runs the backend in development mode with live reloading (using `nodemon`).
