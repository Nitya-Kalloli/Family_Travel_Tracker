# Family Travel Tracker

A web application to track the countries visited by different family members.

## Features

- Track visited countries by family members.
- Add new family members.
- Display the countries visited by each family member.

## Technologies Used

- Node.js
- Express
- PostgreSQL
- EJS (Embedded JavaScript templates)
- Body-parser

## Installation

1. Clone the repository:
    ```bash
    git clone https://github.com/yourusername/family-travel-tracker.git
    ```
2. Navigate to the project directory:
    ```bash
    cd family-travel-tracker
    ```
3. Install the dependencies:
    ```bash
    npm install
    ```
4. Set up your PostgreSQL database and update the database configuration in the code:
    ```javascript
    const db = new pg.Client({
      user: "postgres",
      host: "localhost",
      database: "World",
      password: "yourpassword",
      port: 5432,
    });
    ```

5. Create the required tables in your PostgreSQL database:
    ```sql
    CREATE TABLE users (
        id SERIAL PRIMARY KEY,
        name VARCHAR(100),
        color VARCHAR(50)
    );

    CREATE TABLE countries (
        id SERIAL PRIMARY KEY,
        country_name VARCHAR(100),
        country_code VARCHAR(10)
    );

    CREATE TABLE visited_countries (
        id SERIAL PRIMARY KEY,
        country_code VARCHAR(10) REFERENCES countries(country_code),
        user_id INT REFERENCES users(id)
    );
    ```

## Usage

1. Start the server:
    nodemon index.js
    ```
2. Open your browser and navigate to:
    ```
    http://localhost:2000
    ```

## Project Structure

family-travel-tracker/
│
├── public/
│ └── (static files)
├── views/
│ ├── index.ejs
│ ├── new.ejs
├── index.js
├── package.json
└── README.md

## Routes

- `GET /`: Home page displaying visited countries and users.
- `POST /add`: Add a new visited country for the current user.
- `POST /user`: Switch the current user or add a new user.
- `POST /new`: Add a new user.

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Acknowledgments

- Thanks to the Node.js and Express documentation for guidance.
- Special thanks to PostgreSQL for their powerful database system.

## Contributions
Contributions are welcome! 

## Feedback
Feedback and suggestions are appreciated! If you have any questions, ideas, or issues, please feel free to open an issue on GitHub or contact at nityakalloli.dev@gmail.com