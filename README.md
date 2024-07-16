# Travel Tracker

## Summary

**Technologies Used:**
- Node.js
- Express.js
- PostgreSQL
- pgAdmin 4 (version 16)

**Functionality:**
- Add a country to the list of visited countries.
- Remove a specific country from the list.
- Remove all countries from the list.
- Display the total number of visited countries.

## To Recreate:

**1. Clone the repository**

`git clone https://github.com/yourusername/travel-tracker.git`

`cd travel-tracker`

**2. Install dependencies**

`npm install`

**3. Create .env file**

`cat <<EOT >> .env
DB_PASSWORD=your_postgresql_password
DB_PORT=5432
EOT`

**4. Create the PostgreSQL database and tables**

`psql -U postgres -c "CREATE DATABASE world;"
psql -U postgres -d world -c "
CREATE TABLE countries (
  country_code VARCHAR(3) PRIMARY KEY,
  country_name VARCHAR(255) NOT NULL
);`

`CREATE TABLE visited_countries (
  country_code VARCHAR(3) PRIMARY KEY,
  FOREIGN KEY (country_code) REFERENCES countries (country_code)
);"`

**5. Start the server**

`nodemon index.js`
