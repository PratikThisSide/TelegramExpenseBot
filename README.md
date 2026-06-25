


# 📊 Expense Analyzer Telegram Bot

An AI-powered Telegram Expense Tracker that helps users record daily expenses using natural language, analyze spending habits, manage budgets, track financial goals, and receive automated reminders and reports.

---

# ✨ Features

* 💰 Natural language expense tracking
* 📈 Spending analytics with charts
* 📊 Weekly and monthly financial reports
* 🎯 Budget management
* 🏆 Achievement and XP system
* 🔥 Daily spending streaks
* 🛍️ Wishlist management
* 🎯 Savings goals
* ⏰ Automated reminders
* 📂 Multi-user support
* 📉 Smart spending insights
* 🎨 Interactive Telegram UI using Reply & Inline Keyboards

---

# 📸 Application Screenshots

A preview of the bot's interface and its core features.

## 🖼️ Screenshot 1 – Main Dashboard

![Main Dashboard] <img width="1172" height="993" alt="{8346C174-7753-4967-A0BC-005ECFF5B92F}" src="https://github.com/user-attachments/assets/afe1f680-d7f8-4eba-9df3-28a9a754aa53" />

---

## 🖼️ Screenshot 2

![Expense Tracking] <img width="1198" height="1034" alt="{B72ECC4E-7185-44BB-845B-7448B2F01C37}" src="https://github.com/user-attachments/assets/fe1af2f2-5a09-4e5c-a15b-ed560384aed7" />
)

---

## 🖼️ Screenshot 3 – Analytics

![Analytics & Reports] <img width="1180" height="1034" alt="{43B7062E-3D1F-4706-831F-69BB493421AC}" src="https://github.com/user-attachments/assets/8870d35b-f496-4918-9242-3acb529ef830" />
)

---

## 🖼️ Screenshot 4 – Reports

![Budget & Achievements] <img width="1184" height="1031" alt="{6EC08317-EB77-4812-AB34-6BFCAFA3178D}" src="https://github.com/user-attachments/assets/eee3d78c-2c3a-4b83-b6d1-b4e5943101df" />
)

---

# 🏗️ Project Architecture

The project follows a modular architecture where every file has a single responsibility, making the application scalable and easy to maintain.

```text
expense-tracker-bot/
│── bot.py
│── handlers.py
│── database.py
│── keyboards.py
│── utils.py
│── analytics.py
│── achievements.py
│── scheduler.py
│── requirements.txt
└── README.md
```

## bot.py

The main entry point of the application.

Responsibilities:

* Initializes the SQLite database
* Registers all command handlers
* Registers callback query handlers
* Starts APScheduler
* Launches Telegram polling

---

## handlers.py

Contains all business logic.

Responsible for:

* Command handling
* Natural language expense parsing
* Callback query routing
* Reply keyboard actions
* Expense CRUD operations

---

## database.py

SQLite database wrapper responsible for all database operations.

### Database Tables

* Expenses
* Budgets
* Reminders
* Goals
* Wishlist
* Achievements
* Settings
* Streaks

Each operation uses **user_id**, allowing multiple users to use the bot independently.

---

## keyboards.py

Contains all Reply and Inline Keyboard layouts used throughout the application.

Includes:

* Main Menu
* Budget Menu
* Analytics Menu
* Goals Menu
* Reports
* Settings
* Expense Actions

---

## utils.py

Provides reusable helper functions.

Features include:

* Natural language expense parser
* Automatic category detection
* Date formatting
* Progress bars
* Utility functions

The parser supports multiple regex patterns for flexible expense input.

---

## achievements.py

Gamification module.

Features:

* 14 achievements
* XP rewards
* Automatic achievement checks
* User progression system

---

## analytics.py

Generates spending analytics using Matplotlib.

Supports:

* Pie Charts
* Bar Charts
* Line Charts
* Spending Trends
* Category Analysis
* Smart Suggestions
* Detailed Statistics

Charts are generated in memory and sent directly to Telegram.

---

## scheduler.py

Uses APScheduler for automated tasks.

Scheduled Jobs:

* Daily Reminder (9 PM)
* Weekly Spending Report
* Monthly Financial Report

---

# 🔄 Data Flow

```text
User Message
      │
      ▼
Message Router
      │
      ├── Reply Keyboard Button
      │        │
      │        ▼
      │   Command Handler
      │
      └── Expense Message
               │
               ▼
        Expense Parser
               │
               ▼
      Category Detection
               │
               ▼
       SQLite Database
               │
               ▼
     Achievement Check
               │
               ▼
 Confirmation Message
 (Undo • Edit • Add Another)
```

Inline button clicks are processed through a centralized callback handler, while scheduled jobs independently query the database and send automated notifications.

---

# 💡 Design Decisions

* **SQLite** for lightweight, zero-configuration local storage.
* **APScheduler** for automated background jobs without external cron services.
* **Matplotlib** for generating charts directly in memory.
* **Reply Keyboard** for primary navigation.
* **Inline Keyboard** for contextual actions.
* **User ID-based isolation** for secure multi-user support without requiring authentication.

---

# 🚀 First Run

On the first startup:

1. SQLite database is initialized.
2. All required tables are created automatically.
3. APScheduler registers daily, weekly, and monthly jobs.
4. The bot starts polling the Telegram API.
5. Users can interact using `/start`.
6. The main dashboard displays streaks, levels, and expense statistics.

---

# 🛠️ Tech Stack

* **Language:** Python
* **Framework:** python-telegram-bot
* **Database:** SQLite
* **Scheduler:** APScheduler
* **Visualization:** Matplotlib
* **Image Processing:** BytesIO
* **Async Programming:** asyncio
* **Version Control:** Git & GitHub

---

# 📄 License

This project is open-source and available under the **MIT License**.
