# Sentinel — Security Monitoring

**Academic banking web application with event-driven security monitoring and a SOC dashboard.**

[![Python](https://img.shields.io/badge/Python-3.11+-3776AB?logo=python&logoColor=white)](https://www.python.org/)
[![FastAPI](https://img.shields.io/badge/FastAPI-0.115+-009688?logo=fastapi&logoColor=white)](https://fastapi.tiangolo.com/)
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-15+-4169E1?logo=postgresql&logoColor=white)](https://www.postgresql.org/)
[![Cybersecurity](https://img.shields.io/badge/Focus-Application_Security_%26_SOC-6f42c1)](#security-monitoring)

Sentinel is an academic project developed at **Université de Kara (FAST-LPSIC), during the 2025–2026 academic year**. It simulates a banking environment and demonstrates how application activity can feed a security monitoring workflow.

> **Educational use only.** This project is not a production-ready banking system and has not undergone independent security auditing or regulatory validation.

## Key Features

- **Role-based access control (RBAC):** separate permissions for customers, accounting, management and SOC users.
- **Security event monitoring:** centralized event logging, severity-based alerts and persistent event records.
- **Detection rules:** repeated login failures, suspicious SQL-injection patterns, unauthorized access, username enumeration, unusual access hours and excessive data access.
- **SOC dashboard:** review security events, investigate alerts, monitor locked accounts and receive updates through WebSockets.
- **Automated response:** account locking after repeated failed logins and alert generation for suspicious activity.
- **Sensitive report protection:** role-restricted banking reports and PDF report generation.

## Architecture

Application routers emit security events to an asynchronous Publish/Subscribe dispatcher. Registered handlers apply detection rules, write logs, persist alerts and broadcast updates to the SOC dashboard.

```text
Web application → Security event dispatcher → Detection rules
                                            ├→ Logs and database
                                            ├→ Alerts
                                            └→ WebSocket → SOC dashboard
```

## Technology Stack

- **Backend:** Python, FastAPI, Uvicorn
- **Database / ORM:** PostgreSQL, SQLAlchemy, asyncpg
- **Security:** bcrypt password hashing, session-based authentication, RBAC
- **Monitoring:** asynchronous event handlers, WebSockets, security logs
- **Frontend:** HTML, CSS, JavaScript, Chart.js
- **Reports:** FPDF2

## Run Locally

### Requirements

Python 3.11+, PostgreSQL and Git.

```bash
git clone https://github.com/whitexudan/sentinel-security-monitoring.git
cd sentinel-security-monitoring
python -m venv .venv
source .venv/bin/activate       # Windows: .venv\Scripts\activate
pip install -r requirements.txt
cp env.example .env
```

Set `DATABASE_URL` and a strong, unique `SECRET_KEY` in `.env`. Then initialize the database and start the application:

```bash
psql "$DATABASE_URL" -f init_db.sql
psql "$DATABASE_URL" -f seed_data.sql
uvicorn app.main:app --reload
```

Open `http://localhost:8000`. Use only the local academic environment and test data. Do not commit `.env` or real credentials.

## Project Structure

```text
app/                 Banking application, routes, models and templates
secureDataMonitor/   Event dispatcher, detection rules, logging and WebSockets
init_db.sql          Database schema
seed_data.sql        Sample data
requirements.txt     Python dependencies
env.example          Environment variable template
```

## Scope and Limitations

Sentinel is a learning project for secure web development, event-driven programming and SOC concepts. Its detection rules are application-level heuristics, not a replacement for an enterprise SIEM, IDS/IPS, penetration testing or a formal security assessment. The former Railway demo is currently offline; the source code can be reviewed and run locally.

## Author

<p align="center">
  <strong>TAKOUDA Kokou Trésor</strong> — Cybersecurity Student<br>
  GitHub: <a href="https://github.com/whitexudan">@whitexudan</a>
</p>
