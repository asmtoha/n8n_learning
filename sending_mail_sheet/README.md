📧 Google Sheets → Gmail Automation (Learning Project)

This is a personal learning project where I explored how to automate sending emails using data stored in a Google Sheet.
All contacts used in this project were dummy names and dummy emails — this project is only for learning and testing purposes.

The goal was to understand how the entire workflow works, step by step.

🚀 What This Project Does

This workflow automatically:

Pulls contact data (Name + Email) from a Google Sheet

Sends emails through the Gmail API with clean formatting

Sends a follow-up email asking for available time slots

(Optional) Experiments with adding calendar events

🎯 Why I Built This

This was not built for a business or real outreach.
I built it to learn:

how Google Sheets API works

how Gmail API works

how to build email templates programmatically

how to structure simple follow-up logic

how different automation steps connect together

🧩 Project Architecture
Google Sheets → Data Fetch → Gmail API → Follow-Up Logic → (Optional) Calendar Integration


Google Sheets
Stores dummy contact data (Name, Email).

Data Fetch Script
Reads new rows and avoids duplicates.

Gmail API
Sends formatted emails automatically.

Follow-Up Logic
Sends a second email after a delay.

Calendar (Optional)
Basic experiment with adding events.

🛠 Tech/Tools Used

Google Sheets API

Gmail API

Python (or Apps Script — depending on your implementation)

OAuth credentials

Basic scheduling logic

You can edit this section to match your exact stack.

📑 Features

Pulls only new rows from Sheets

Sends clean, formatted emails

Prevents duplicate sends

Sends follow-ups automatically

Uses dummy data for safe testing

Beginner-friendly automation flow

📁 Project Structure (Example)
├── README.md
├── sheets_fetch.py
├── gmail_send.py
├── followup_logic.py
├── credentials/
│   └── oauth_credentials.json
└── templates/
    └── email_template.txt


Adjust this based on your actual file names.

🧪 How to Run

Clone this project

Set up Google Cloud project & enable:

Google Sheets API

Gmail API

Download OAuth credentials

Install dependencies

Run the scripts in order or automate them with a scheduler

📚 What I Learned

How to authenticate using Google APIs

How data flows through an automation pipeline

How to design email templates with proper formatting

How to handle follow-up logic

How small automations have many steps behind the scenes

Why debugging is half the work

📝 Notes

This project uses ONLY dummy email addresses

Not intended for real outreach

Built purely for automation practice

Feel free to fork, copy, or modify for your own learning

🤝 Connect

If you’re learning automation, APIs, or building small personal workflows, feel free to connect or raise issues here.
I’m documenting my journey step by step.