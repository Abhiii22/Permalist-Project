# Permalist - A Persistent To-Do List

A simple, yet powerful, to-do list web application that saves your tasks permanently. Built with Node.js, Express, EJS, and backed by a PostgreSQL database for persistent storage.


## ✨ Features

* **View All Tasks**: See a clear list of all your current to-do items.
* **Add New Tasks**: Quickly add new items to your list.
* **Edit Existing Tasks**: Click on any task to update its title.
* **Delete Tasks**: Remove completed or unwanted tasks with a single click.
* **Persistent Storage**: Your tasks are saved in a PostgreSQL database, so they'll be there every time you come back.

---

## 🛠️ Tech Stack

This project is built using the following technologies:

* **Backend**: Node.js, Express.js
* **Database**: PostgreSQL
* **Templating Engine**: EJS (Embedded JavaScript)
* **Middleware**: body-parser for handling form data.
* **Node-Postgres (`pg`)**: The non-blocking PostgreSQL client for Node.js.

---

## 🚀 Getting Started

Follow these instructions to get a local copy up and running.

### Prerequisites

Make sure you have the following installed on your machine:
* [Node.js](https://nodejs.org/) (which includes npm)
* [PostgreSQL](https://www.postgresql.org/download/)

### Installation & Setup

1.  **Clone the repository:**
    ```sh
    git clone <your-repository-url>
    ```

2.  **Navigate to the project directory:**
    ```sh
    cd permalist-project
    ```

3.  **Install NPM packages:**
    ```sh
    npm install
    ```

4.  **Set up the PostgreSQL Database:**
    * Open your PostgreSQL terminal (`psql`).
    * Create a new database.
        ```sql
        CREATE DATABASE Permalist;
        ```
    * Connect to your new database.
        ```sql
        \c Permalist
        ```
    * Run the `queries.sql` script to create the necessary table and add some initial data. You can copy and paste the contents of the file into your `psql` terminal.
        ```sql
        CREATE TABLE items (
          id SERIAL PRIMARY KEY,
          title VARCHAR(100) NOT NULL
        );

        INSERT INTO items (title) VALUES ('Buy milk'), ('Finish homework');
        ```

5.  **Update Database Credentials:**
    * Open the `solution.js` file.
    * Locate the `db` client configuration and update the `user`, `host`, `database`, `password`, and `port` to match your PostgreSQL setup.

    ```javascript
    const db = new pg.Client({
      user: "your_postgres_user",
      host: "localhost",
      database: "Permalist",
      password: "your_password",
      port: 5432,
    });
    ```

---

## 🏃‍♀️ Usage

1.  **Start the server:**
    ```sh
    npm start
    ```
    You should see the message `Server running on port 3000` in your console.

2.  **Open the application:**
    Open your web browser and navigate to `http://localhost:3000`.

You can now add, edit, and delete items in your persistent to-do list!

---

## 📂 File Structure

```
.
├── solution.js         # Main server file with Express logic and DB queries
├── queries.sql         # SQL script for database setup
├── package.json        # Project metadata and dependencies
├── public/             # Static assets (CSS, images, etc.)
│   └── styles/
│       └── main.css
└── views/              # EJS templates
    └── index.ejs
```
