# Expense Tracker

A multi-user expense tracking web app built with Flask and MySQL. Each user registers an account and manages their own expenses.

## Features

- Register, login and logout (passwords are stored as hashes)
- Add, edit and delete expenses (amount, category, note, date)
- Each user only sees their own expenses
- Total spent and spending-by-category chart (Chart.js)

## Tech Stack

- Python, Flask
- MySQL (via `mysql-connector-python`)
- HTML, CSS, JavaScript, Chart.js

## Setup

1. **Clone the repository**

   ```
   git clone https://github.com/Malshi123/Expense-Tracker.git
   cd Expense-Tracker
   ```

2. **Install the dependencies**

   ```
   python3 -m pip install -r requirements.txt
   ```

3. **Create the database**

   Start MySQL (for example with XAMPP), then run the SQL in `schema.sql` (for example in phpMyAdmin's SQL tab). It creates the `Expense_tracker` database with the `users` and `expenses` tables.

4. **Create your `.env` file**

   Copy `.env.example` to `.env` and fill in your own values:

   ```
   SECRET_KEY=your-own-long-random-text
   DB_HOST=localhost
   DB_USER=root
   DB_PASSWORD=
   DB_NAME=Expense_tracker
   ```

   You can generate a secret key with:

   ```
   python3 -c "import secrets; print(secrets.token_hex(32))"
   ```

5. **Run the app**

   ```
   python3 app.py
   ```

   Open http://127.0.0.1:5000 in your browser, register an account and log in.

## Project Structure

```
Expense Tracker/
├── app.py              # Flask app (routes, database access)
├── schema.sql          # Database tables
├── requirements.txt    # Python dependencies
├── .env.example        # Example environment variables
├── Expense_Tracker.py  # Original terminal version of the tracker
├── test_db.py          # Small script to test the MySQL connection
├── static/             # CSS files
└── templates/          # HTML templates
```

## Notes

- The `.env` file holds secrets and is not committed to Git.
- The default XAMPP MySQL user (`root` with no password) is for local development only.