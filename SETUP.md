# Django project setup

Created the `thewebsix` project with Django's default `startproject` command and
registered four empty apps generated with `startapp`:

| App | Intended responsibility |
| --- | --- |
| `accounts` | Registration and profiles, using Django's built-in user model |
| `hikes` | Hikes, guides, saved hikes and announcements |
| `bookings` | Reservations, participants and payment status |
| `community` | Moments/posts, comments, likes, reviews and Q&A |

These are starter folders only; no custom models, pages or functionality have
been implemented. The specification was used only to identify app boundaries.

SQLite, authentication, `/admin/`, middleware and all other generated settings
remain at their Django defaults. No custom admin dashboard was added.

Added `requirements.txt` to pin Django to 6.1.1 and `.gitignore` to exclude local
virtual environments, Python caches and SQLite databases from Git.

## Run locally

Use Python 3.12 or newer (setup checked with Python 3.14).

```powershell
git clone https://github.com/farhaanbg/TheWebsix.git
cd TheWebsix
python -m venv .venv
.venv\Scripts\Activate.ps1
python -m pip install -r requirements.txt
python manage.py migrate
python manage.py createsuperuser
python manage.py runserver
```

On macOS/Linux, activate with `source .venv/bin/activate` instead.
Open http://127.0.0.1:8000/ for Django's welcome page and
http://127.0.0.1:8000/admin/ for the default admin login.

Each teammate creates their own local SQLite database and superuser. Commit
future app migrations, but do not commit the database or virtual environment.

## Verification

Run `python manage.py check` and `python manage.py migrate` to check the setup
and initialize the default database tables.
