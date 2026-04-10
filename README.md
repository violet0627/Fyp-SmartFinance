# SmartFinance

A personal finance management app built with Flutter and Python Flask. Designed to help users track income and expenses, manage budgets, set savings goals, and monitor investments — all in one place.

---

## Features

- **Authentication** — Register, login, email verification, password reset
- **Two-Factor Authentication** — Email-based 2FA with backup codes
- **Transaction Tracking** — Log income and expenses with categories
- **Budget Management** — Set monthly budgets per category with alerts when nearing limits
- **Savings Goals** — Create goals, contribute funds, and track progress
- **Investment Portfolio** — Track stocks, crypto, unit trusts, and other asset types
- **Financial Insights** — Calculates a financial health score based on savings rate, budget adherence, spending consistency, and goal progress
- **Reports & Analytics** — Charts and trends for spending and income over time
- **Recurring Transactions** — Schedule repeating income or bill entries
- **Gamification** — XP, levels, achievements, and daily streaks to encourage good financial habits
- **Dark Mode** — Full dark/light theme support
- **Receipt Scanner** — Scan receipts to auto-fill transaction details

---

## Tech Stack

**Backend**
- Python 3.x, Flask
- MySQL 8.0, SQLAlchemy
- JWT authentication, bcrypt password hashing
- Flask-Mail for email services

**Frontend**
- Flutter / Dart
- Material Design
- fl_chart for data visualisation
- shared_preferences for local storage

---

## Project Structure

```
smartfinance/
├── backend/
│   ├── app/
│   │   ├── models/        # SQLAlchemy database models
│   │   ├── routes/        # Flask API blueprints
│   │   └── utils/         # JWT, email, 2FA helpers
│   ├── migrations/        # SQL migration scripts
│   ├── config.py
│   └── run.py
│
├── lib/
│   ├── models/            # Dart data models
│   ├── screens/           # All app screens
│   ├── services/          # API calls and business logic
│   ├── widgets/           # Reusable UI components
│   ├── utils/             # Theme, colours, categories
│   └── main.dart
│
└── database/
    └── schema.sql         # Full database schema
```

---

## Getting Started

### Requirements

- Python 3.8+
- Flutter 3.0+
- MySQL 8.0+

### Backend Setup

```bash
cd backend

# Install dependencies
pip install -r requirements.txt

# Create a .env file (see .env.example for reference)
cp .env.example .env

# Start the Flask server
python run.py
```

### Database Setup

```bash
# Create the database
mysql -u root -p -e "CREATE DATABASE smartfinance;"

# Import schema
mysql -u root -p smartfinance < database/schema.sql

# Run migrations
mysql -u root -p smartfinance < backend/migrations/add_two_factor_auth.sql
mysql -u root -p smartfinance < backend/migrations/email_verification.sql
```

### Frontend Setup

```bash
# Install Flutter dependencies
flutter pub get

# Run the app
flutter run -d chrome        # Web
flutter run                  # Mobile emulator
```

---

## Configuration

Copy `backend/.env.example` to `backend/.env` and fill in your values:

```env
DB_HOST=localhost
DB_PORT=3306
DB_USER=root
DB_PASSWORD=your_password
DB_NAME=smartfinance

FLASK_APP=run.py
SECRET_KEY=your_secret_key

PORT=5000
```

---

## License

MIT
