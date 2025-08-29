
Personal Social Dashboard (local) — Demo project

Features:
- Register / Login (local users)
- Add social accounts and store API key (demo; store safely in production)
- Create drafts and schedule posts with local timezone Europe/Berlin
- APScheduler (background) schedules jobs stored in jobs.db (SQLite)
- mock_publish simulates publishing and writes logs (NO external calls)

Run locally:
1. create a Python venv and install requirements:
   pip install -r requirements.txt
2. Run app.py:
   python app.py
3. Open http://localhost:5000
4. To test scheduling: add an account, create a draft or paste content, set 'وقت التنفيذ' to a few minutes from now (Europe/Berlin local time) and submit.
   The scheduler will run the job at that UTC time and write an entry to 'سجل النشر'.

Security notes:
- This is a demo: API keys are stored plaintext in the DB. For production, encrypt them or use a secrets manager.
- The scheduler uses a jobs.db SQLite file to persist scheduled jobs between restarts.
