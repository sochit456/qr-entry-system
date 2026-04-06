# QR-Based College Entry System

A FastAPI + SQLite web application for student registration, QR code generation, gate scanning, and admin monitoring during college events.

## Features

- Student registration with unique roll number validation
- Token-only QR code generation using the `qrcode` library
- Single-use entry verification in real time
- Mobile-friendly scanner page using `html5-qrcode`
- Admin panel with search, filter, and timestamp visibility

## Project Structure

```text
project/
|-- backend/
|   |-- __init__.py
|   |-- database.py
|   |-- main.py
|   |-- models.py
|   |-- schemas.py
|   |-- utils.py
|-- frontend/
|   |-- admin.html
|   |-- index.html
|   |-- scanner.html
|   |-- script.js
|   |-- style.css
|-- qr_codes/
|-- database.db
|-- requirements.txt
```

## Setup

1. Build Command:
```powershell
pip install -r requirements.txt
```

2. Start Command::

```powershell
uvicorn backend.main:app --host 0.0.0.0 --port 10000
```
3. Service → Environment → Add Variable:
```powershell
 Key: DATABASE_URL
Value: (paste your postgres URL)
```

## API Endpoints

- `POST /register`
- `POST /verify`
- `GET /students`
- `GET /health`

## Notes

- QR images are stored inside `qr_codes/`.
- The scanner page loads `html5-qrcode` from a CDN, so internet access is needed for the scanner library unless you vendor it locally.
- `database.db` is created automatically if it does not exist.
