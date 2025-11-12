Login-Alert
A small, practical tool that emails login time and current user information when run. Built in Python and easy to convert to a Windows executable for one‑click usage. Clean, minimal, and made for quick deployment on personal machines or small internal setups.

Key Features
Sends an email containing the current date/time (12‑hour format with AM/PM) and the current OS user

Works with Gmail SMTP (supports App Passwords)

Single‑file runnable Python script that can be packaged into an .exe for Windows

Simple folder layout: keep source in src/ and built binaries in exe/

Safe defaults and a reminder to never commit secrets

Getting Started
Prerequisites
Python 3.7+ installed on your machine

A Gmail account with a generated App Password (recommended)

git (optional, for repo workflow)

Local setup (quick)
Clone the repo or open the project folder.

Create and activate a virtual environment (optional but recommended):

Windows (PowerShell)

Code
python -m venv .venv
.venv\Scripts\Activate.ps1
Linux / macOS

Code
python -m venv .venv
source .venv/bin/activate
Install dependencies (none external required for the basic script; standard library used). If you later add packages, install with:

Code
pip install -r requirements.txt
Configure credentials (secure)
Do NOT commit your app password or any credentials.

Preferred: set environment variables before running:

Windows (CMD)

Code
set APP_PASSWORD=your_app_password
set SENDER_EMAIL=you@example.com
set RECEIVER_EMAIL=you@example.com
Linux / macOS

Code
export APP_PASSWORD="your_app_password"
export SENDER_EMAIL="you@example.com"
export RECEIVER_EMAIL="you@example.com"
If you must test locally without env vars, the script can be edited to place the App Password inline for personal testing only (never push to Git).

Build EXE (Windows) — quick guide
Install PyInstaller:

Code
pip install pyinstaller
From the project root (where your main script lives), run:

Code
python -m PyInstaller --onefile src/your_script.py
Replace your_script.py with the actual script filename (e.g., email_login.py).

To hide the console window: add --noconsole.

To add an icon: add --icon=app.ico.

After build completes, grab the executable from:

Code
dist/your_script.exe
Move the .exe into the exe/ folder in the repo for organization.

Note: If pyinstaller is unrecognized, use python -m PyInstaller ... as shown.
