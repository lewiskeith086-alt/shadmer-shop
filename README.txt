SHADMER SHOP WEB APP - VERSION 2
================================

WHAT IS INCLUDED
----------------
1. Admin and attendant login
2. Modern ladies-shop design with large buttons
3. Sales entry page
4. Restock page
5. Inventory page
6. Daily report page with CSV export
7. Render-ready deployment files

DEFAULT LOGIN
-------------
Admin
- username: admin
- password: admin123

Attendant
- username: attendant
- password: attendant123

IMPORTANT
---------
Change these passwords after first login by editing users in the database or extending the app later.

RUN LOCALLY
-----------
1. Open terminal in this folder
2. Install requirements:
   pip install -r requirements.txt
3. Run:
   python app.py
4. Open browser:
   http://127.0.0.1:5000

RENDER DEPLOY
-------------
Option A - easiest
1. Upload this project to a GitHub repo
2. In Render, create a new Blueprint instance
3. Point it to the repo
4. Render will read render.yaml and create:
   - web service
   - PostgreSQL database
5. After deploy, open the Render URL

Option B - manual
1. Create PostgreSQL on Render
2. Create Web Service on Render
3. Build command:
   pip install -r requirements.txt
4. Start command:
   gunicorn app:app
5. Add env vars:
   SECRET_KEY = any long random text
   DATABASE_URL = your Render Postgres connection string

NOTES
-----
- Local run uses SQLite by default.
- Render should use PostgreSQL for proper remote multi-user access.
- Inventory auto-imports from SHADMER.xlsx on first run when database is empty.
