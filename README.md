# Meeting Feedback Telegram Bot

A lightweight Telegram bot built with **Aiogram 3** and **SQLite3** designed to collect and store corporate employee feedback after meetings. It measures meeting effectiveness and emotional satisfaction (CSI) using a finite state machine (FSM).

## 🚀 Features
* **User Authentication:** Automatically checks if an employee's full name (FIO) exists in the database before granting access.
* **FSM-driven Questionnaire:** Step-by-step interview wizard with data confirmation and editing blocks.
* **Database Integration:** Relational SQLite structure (tables: empls, meets, fback) with foreign keys.
* **Interactive UI:** Smooth user experience powered by dynamic Reply Keyboards.

## 🛠️ Tech Stack
* **Language:** Python 3.11+
* **Framework:** Aiogram 3.x
* **Database:** SQLite3
* **State Management:** Built-in FSM (MemoryStorage)

## 📊 Database Schema
The project uses a relational database named fback.db with three connected tables:
* empls: Stores employee full names and maps them to their unique Telegram IDs (t_id).
* meets: Logs meeting details including titles and date/time.
* fback: Connects employees and meetings with metrics (effectiveness and satisfaction scores from 1 to 5).

## 📦 Installation & Setup

1. Clone the repository:
git clone https://github.com/foenichka/Rate_botik.git
cd Rate_botik

2. Install dependencies:
pip install aiogram

3. Configure the Token:
Open the main script and insert your Telegram Bot API token into the token_b variable:
token_b = "YOUR_TELEGRAM_BOT_TOKEN"

4. Run the bot:
python main.py

## 📝 How to Test (Note for Reviewers)
Since the bot enforces an authorization check against the empls table, you need to manually insert at least one employee row into fback.db before running /start, or modify the database initialization logic to skip this check for testing.