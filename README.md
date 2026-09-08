# SecureDataMonitor

> **Web application with real-time security monitoring and event-driven threat detection.**

[![Python](https://img.shields.io/badge/Python-3.13+-3776AB?logo=python\&logoColor=white)](https://www.python.org/)
[![FastAPI](https://img.shields.io/badge/FastAPI-0.115+-009688?logo=fastapi\&logoColor=white)](https://fastapi.tiangolo.com/)
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-15+-4169E1?logo=postgresql\&logoColor=white)](https://www.postgresql.org/)
[![SQLAlchemy](https://img.shields.io/badge/SQLAlchemy-2.0-D71F00?logo=sqlalchemy\&logoColor=white)](https://www.sqlalchemy.org/)
[![WebSocket](https://img.shields.io/badge/WebSocket-Real--Time-black)](https://developer.mozilla.org/en-US/docs/Web/API/WebSockets_API)
[![Security](https://img.shields.io/badge/Focus-Cybersecurity-6f42c1)](#-security-monitoring)
[![Academic](https://img.shields.io/badge/Project-Academic-blue)](#-academic-context)

**Xud-Bank** is an academic banking web application designed to combine **secure application development** with a **real-time SOC-oriented monitoring system**.

The project implements role-based access control, security event collection, automated threat detection, real-time alerting through WebSockets, account locking, and security reporting.

> **Academic project — University of Kara, 2nd Year Bachelor’s degree in Computer Security & Cybersecurity — 2025**

---

## 👨‍💻 Author

**TAKOUDA KOKOU TRÉSOR**

Cybersecurity Student

GitHub:
https://github.com/whitexudan15

---

## 🎓 Academic Context

This project was developed as part of an academic cybersecurity and event-driven programming project at:

**Université de Kara — FAST-LPSIC**

Academic year:

**2025–2026**

The project focuses on applying software engineering concepts to a security-oriented use case, particularly:

* event-driven programming
* asynchronous processing
* web application security
* RBAC
* security monitoring
* intrusion detection concepts
* security logging
* real-time alerting

---

## ⚠️ Disclaimer

Xud-Bank is an **academic and educational project**.

It is **not intended to be used as a real banking system** and has not undergone the security, compliance, availability and operational validation required for production financial software.

A production deployment would require additional controls such as:

* hardened infrastructure
* HTTPS/TLS everywhere
* secure secret management
* WAF
* IDS/IPS
* centralized SIEM
* stronger authentication and MFA
* comprehensive audit trails
* penetration testing
* external security audits
* backup and disaster recovery
* regulatory and compliance controls

---

## 📚 What This Project Demonstrates

This project demonstrates the ability to design and implement a web application where **security monitoring is part of the application architecture rather than an external afterthought**.

The main technical concepts demonstrated are:

```text
Secure Web Application
        +
RBAC / Segregation of Duties
        +
Event-Driven Architecture
        +
Threat Detection
        +
Security Logging
        +
Real-Time Alerting
        +
SOC Monitoring
```

This makes the project particularly relevant to **Web Security, SOC and Blue Team-oriented learning**.

---

## 🎯 Project Overview

Xud-Bank simulates a banking environment where different users interact with separate business areas according to their roles.

The main objective was not only to build a banking application, but also to demonstrate how **application security events can be collected, analyzed and transformed into actionable SOC alerts**.

The application therefore combines two complementary aspects:

* **Secure Web Application**
* **Security Monitoring / SOC Engine**

### Key Features

* 🔐 Secure authentication and session management
* 👥 Role-Based Access Control (**RBAC**)
* 🛡️ Segregation of Duties between business roles
* 🚨 Automated security event detection
* 📡 Real-time SOC monitoring through WebSockets
* 🔎 Detection of brute-force attempts
* 💉 SQL injection pattern detection
* 🚫 Unauthorized access detection
* 📊 Mass data access / suspected exfiltration detection
* 👤 Username enumeration detection
* 🌙 Off-hours access monitoring
* 📁 Sensitive banking report protection
* 🔒 Automatic account locking
* 📄 Security-aware PDF report generation
* 📝 Persistent security event logging
* 📈 SOC statistics and alert management

---

## 🧠 Security Monitoring Concept

The main component of the project is **SecureDataMonitor**.

Instead of treating security as an isolated feature, application actions generate security events that are processed by an asynchronous event engine.

```text
                    ┌──────────────────────┐
                    │      Web Request      │
                    └──────────┬───────────┘
                               │
                               ▼
                    ┌──────────────────────┐
                    │      Application     │
                    │       Router         │
                    └──────────┬───────────┘
                               │
                         Security Event
                               │
                               ▼
                    ┌──────────────────────┐
                    │   Event Dispatcher   │
                    │       Pub/Sub        │
                    └──────────┬───────────┘
                               │
             ┌─────────────────┼─────────────────┐
             ▼                 ▼                 ▼
       ┌──────────┐      ┌──────────┐      ┌─────────────┐
       │ Detection│      │  Logger  │      │ WebSocket   │
       │  Engine  │      │          │      │ Broadcast   │
       └────┬─────┘      └────┬─────┘      └──────┬──────┘
            │                 │                   │
            ▼                 ▼                   ▼
       ┌──────────┐      ┌──────────┐      ┌─────────────┐
       │  Alert   │      │ Database │      │ SOC Dashboard│
       └──────────┘      └──────────┘      └─────────────┘
```

This architecture makes it possible to keep security monitoring separated from the main business logic while still reacting to application activity in real time.

---

## 🏗️ Architecture

The project follows a **layered architecture** combined with an **event-driven architecture**.

### Layered Architecture

```text
┌───────────────────────────────────────────────┐
│                 PRESENTATION                  │
│     Routers / Templates / WebSockets          │
├───────────────────────────────────────────────┤
│                    BUSINESS                   │
│       Authentication / Banking Logic          │
├───────────────────────────────────────────────┤
│                  EVENT-DRIVEN                 │
│      Dispatcher / Detection / Alerts          │
├───────────────────────────────────────────────┤
│                  PERSISTENCE                  │
│       SQLAlchemy / PostgreSQL / Logs          │
└───────────────────────────────────────────────┘
```

### Design Patterns

The application mainly relies on:

* **Layered Architecture**
* **Observer / Publish-Subscribe**
* **Service Layer**
* **Role-Based Access Control**
* **Event-driven processing**

---

## 🛠️ Technology Stack

| Area                    | Technology               |
| ----------------------- | ------------------------ |
| Backend                 | Python / FastAPI         |
| Database                | PostgreSQL               |
| ORM                     | SQLAlchemy 2.0           |
| Async Driver            | asyncpg                  |
| Authentication          | Passlib / Bcrypt         |
| Sessions                | itsdangerous             |
| Real-time communication | Native WebSockets        |
| PDF generation          | FPDF2                    |
| Frontend                | HTML5 / CSS / JavaScript |
| Charts                  | Chart.js                 |
| Deployment              | Railway / local          |
| Server                  | Uvicorn / Gunicorn       |

---

## 📁 Project Structure

```text
xud-bank/
│
├── app/
│   ├── main.py
│   │
│   ├── database.py
│   │
│   ├── models/
│   │   └── ...
│   │
│   ├── routers/
│   │   ├── auth.py
│   │   ├── soc.py
│   │   ├── direction.py
│   │   ├── comptabilite.py
│   │   └── client.py
│   │
│   ├── services/
│   │   ├── auth_service.py
│   │   └── report_service.py
│   │
│   ├── templates/
│   │   ├── base.html
│   │   ├── login.html
│   │   ├── errors/
│   │   ├── soc/
│   │   ├── direction/
│   │   ├── comptabilite/
│   │   └── client/
│   │
│   └── static/
│       └── css/
│
├── secureDataMonitor/
│   ├── events/
│   │   ├── dispatcher.py
│   │   └── handlers.py
│   │
│   ├── services/
│   │   ├── detection.py
│   │   └── logger.py
│   │
│   ├── routers/
│   │   ├── api_alerts.py
│   │   └── admin.py
│   │
│   ├── static/
│   │   └── js/
│   │       └── ws_alerts.js
│   │
│   └── templates/
│
├── logs/
│   └── security.log
│
├── init_db.sql
├── seed_data.sql
├── requirements.txt
├── env.example
├── Procfile
├── .gitignore
└── README.md
```

---

## 👥 Authentication & RBAC

The application implements strict role separation.

### Roles

| Role        | Main responsibility                         |
| ----------- | ------------------------------------------- |
| `client`    | Personal banking operations                 |
| `comptable` | Banking/accounting operations               |
| `directeur` | Management and full reporting               |
| `soc`       | Security monitoring and incident management |

Each role has access only to the resources required for its responsibilities.

This implements a basic **Segregation of Duties (SoD)** model.

### Example

A `comptable` can access accounting reports but cannot access the management report containing secret accounts.

Attempting to access a restricted resource results in:

```text
HTTP 403 Forbidden
        +
Security Event
        +
CRITICAL Alert
        +
SOC WebSocket Notification
```

---

## 🚨 Security Monitoring

SecureDataMonitor processes application events and applies detection rules to them.

### Security Events

The system supports events such as:

| Event                  | Description                        | Severity |
| ---------------------- | ---------------------------------- | -------- |
| `login_success`        | Successful login                   | LOW      |
| `login_failed`         | Failed login                       | MEDIUM   |
| `account_locked`       | Account locked                     | MEDIUM   |
| `unknown_user`         | Unknown username                   | MEDIUM   |
| `unauthorized`         | Unauthorized access                | HIGH     |
| `privilege_escalation` | Privilege escalation attempt       | HIGH     |
| `rate_limit`           | Rate-limit event                   | MEDIUM   |
| `mass_data_access`     | Excessive data access              | CRITICAL |
| `off_hours_access`     | Access outside allowed hours       | LOW      |
| `sql_injection`        | SQL injection pattern detected     | HIGH     |
| `enum_attempt`         | Username enumeration               | MEDIUM   |
| `suspicious_url`       | Suspicious URL detected            | HIGH     |
| `bank_fraud_attempt`   | Unauthorized banking report access | CRITICAL |

---

## 🔎 SOC Detection Rules

The monitoring engine implements seven main detection policies.

### Rule 1 — Brute Force

Detects repeated authentication failures.

```text
3 failed login attempts
        ↓
within 2 minutes
        ↓
Account automatically locked
        ↓
MEDIUM alert
```

---

### Rule 2 — SQL Injection

Detects common SQL injection patterns in user-controlled parameters.

Examples include:

```text
' OR 1=1
UNION SELECT
; DROP
```

The application rejects suspicious input and records the security event.

Severity:

```text
HIGH
```

---

### Rule 3 — Unauthorized Access

Detects attempts by users to access administrative or SOC resources without the required role.

Example:

```text
client → /soc/dashboard
```

Expected behavior:

```text
403 Forbidden
+
HIGH security alert
```

---

### Rule 4 — Mass Data Access

Detects excessive access to application data.

Example threshold:

```text
> 20 accesses
within < 1 minute
```

The behavior is flagged as potential data exfiltration.

Severity:

```text
CRITICAL
```

---

### Rule 5 — Username Enumeration

Detects multiple username discovery attempts originating from the same IP.

Example:

```text
3 different usernames
within 5 minutes
from the same IP
```

Severity:

```text
MEDIUM
```

---

### Rule 6 — Off-Hours Access

Monitors authentication activity outside the configured working hours.

Default configuration:

```text
Allowed hours: 07:00 → 20:00 UTC
```

The event is recorded for monitoring and investigation.

Severity:

```text
LOW
```

---

### Rule 7 — Banking File Theft

Protects sensitive banking reports from unauthorized roles.

Example:

```text
Comptable
    │
    └──> /direction/rapport
              │
              ▼
        Access denied
              │
              ├── HTTP 403
              ├── CRITICAL alert
              ├── Security event
              └── Real-time SOC notification
```

This is one of the main security scenarios implemented by the project.

---

## ⚡ Event-Driven Engine

The application uses an asynchronous dispatcher based on a Publish/Subscribe model.

A router can emit an event without directly handling all the security consequences.

Conceptually:

```python
await dispatcher.emit(
    "bank_fraud_attempt",
    {
        "ip": "192.168.1.100",
        "username": "user",
        "role": "comptable",
        "path": "/direction/rapport"
    }
)
```

The dispatcher then forwards the event to subscribed handlers.

Handlers can:

* write the event to the security log
* create a security alert
* broadcast the alert through WebSockets
* update monitoring statistics
* trigger automated security actions

This separation makes the security monitoring layer easier to extend.

---

## 📡 Real-Time SOC Dashboard

The `/soc/dashboard` interface provides real-time visibility into security activity.

### Monitoring capabilities

* Security event frequency
* Severity distribution
* Suspicious IP addresses
* Latest unresolved alerts
* Latest security events
* Global event counters
* Number of active alerts
* Locked accounts

The dashboard receives events through:

```text
WebSocket
    ↓
Batching
    ↓
requestAnimationFrame
    ↓
UI update
```

This avoids continuously reloading the page and allows security events to appear in near real time.

---

## 📊 Severity Model

| Severity | Purpose                    | Examples                             |
| -------- | -------------------------- | ------------------------------------ |
| LOW      | Informational activity     | Successful login, off-hours access   |
| MEDIUM   | Suspicious behavior        | Brute force, enumeration             |
| HIGH     | Confirmed security concern | SQL injection, unauthorized access   |
| CRITICAL | Major security incident    | Mass data access, banking file theft |

---

## 📄 Banking Reports

The application generates structured PDF reports based on security classifications.

### Management Report

Endpoint:

```text
GET /direction/rapport
```

Access:

```text
Director only
```

The report contains:

* PUBLIC accounts
* CONFIDENTIAL accounts
* SECRET accounts
* Global statistics
* Section subtotals
* Account information
* Creation/update timestamps

---

### Accounting Report

Endpoint:

```text
GET /comptabilite/rapport
```

Access:

```text
Accountant + Director
```

The report contains:

* PUBLIC accounts
* CONFIDENTIAL accounts

SECRET accounts are excluded.

This demonstrates how access control can also be applied to generated business documents.

---

## 🌐 Main Routes

### Authentication

```text
GET  /auth/login
POST /auth/login
GET  /auth/logout
GET  /auth/register
POST /auth/register
```

Registration is disabled in the deployed configuration.

### SOC

```text
GET  /soc/dashboard
GET  /soc/users
GET  /soc/alerts
GET  /soc/events
GET  /soc/logs/raw

POST /soc/alerts/{id}/resolve
POST /soc/users/{id}/lock
POST /soc/users/{id}/unlock
```

### Management

```text
GET  /direction/dashboard
GET  /direction/users
GET  /direction/accounts
GET  /direction/rapport

POST /direction/users/new
POST /direction/users/{id}/delete
```

### Accounting

```text
GET  /comptabilite/dashboard
POST /comptabilite/accounts/create
GET  /comptabilite/rapport
```

### Customer

```text
GET  /client/dashboard
POST /client/transfers
GET  /client/history
```

### WebSocket

```text
WS /ws/alerts
```

### Health Check

```text
GET /health
```

---

## 🗄️ Data Model

The application uses PostgreSQL as its persistence layer.

The database stores both business information and security monitoring information.

Important entities include:

* users
* bank accounts
* transactions
* security events
* alerts

Security monitoring data is persisted so that incidents can be reviewed after they occur.

Indexes are used on important security fields such as:

```text
timestamp
severity
event_type
```

---

## 📝 Logging

Security visibility is provided at three levels.

### 1. Local Security Log

```text
logs/security.log
```

Used for:

* forensic analysis
* troubleshooting
* post-incident review
* security auditing

### 2. SOC Dashboard

Real-time visualization of:

* events
* alerts
* severity
* suspicious IPs
* recent incidents

### 3. Database

Security events and alerts are persisted in PostgreSQL.

This provides historical visibility even after the real-time alert has disappeared from the dashboard.

---

## 🧪 Security Test Scenarios

The project includes reproducible scenarios for validating the detection engine.

### Brute Force

```bash
for i in {1..4}; do
  curl -X POST http://localhost:8000/auth/login \
    -d "email=user@example.com&password=WrongPassword"
done
```

Expected behavior:

```text
3 failed attempts
        ↓
Account locked
        ↓
MEDIUM alert
```

### SQL Injection Detection

```bash
curl -X POST http://localhost:8000/auth/login \
  -d "email=admin' OR '1'='1&password=test"
```

Expected behavior:

```text
400 Bad Request
+
HIGH alert
+
Payload logged
```

### Unauthorized Banking Report Access

```bash
curl http://localhost:8000/direction/rapport \
  -b cookies_comptable.txt
```

Expected behavior:

```text
403 Forbidden
+
CRITICAL alert
+
Real-time SOC notification
```

### Mass Data Access

```python
import requests

session = requests.Session()

for _ in range(25):
    session.get(
        "http://localhost:8000/comptabilite/dashboard"
    )
```

Expected behavior:

```text
>20 accesses within 1 minute
        ↓
CRITICAL alert
        ↓
MASS_DATA_ACCESS event
```

---

## 🚀 Installation

### Requirements

* Python 3.11+
* PostgreSQL
* pip
* Git

### Clone

```bash
git clone https://github.com/whitexudan15/xud-bank.git
cd xud-bank
```

### Create virtual environment

```bash
python -m venv .venv
source .venv/bin/activate
```

Windows:

```powershell
.venv\Scripts\activate
```

### Install dependencies

```bash
pip install -r requirements.txt
```

### Configure environment

```bash
cp env.example .env
```

Configure the database and application secrets in `.env`.

Example:

```env
DATABASE_URL=postgresql+asyncpg://user:password@host:5432/database

SECRET_KEY=your-long-random-secret-key

BRUTE_FORCE_WINDOW=120
MAX_LOGIN_ATTEMPTS=3

MASS_ACCESS_WINDOW=60
MASS_ACCESS_LIMIT=20

ENUM_WINDOW=300
ENUM_USERNAMES_LIMIT=3

ALLOWED_HOURS_START=7
ALLOWED_HOURS_END=20

LOG_FILE_PATH=logs/security.log
```

### Initialize database

```bash
psql $DATABASE_URL < init_db.sql
psql $DATABASE_URL < seed_data.sql
```

### Start the application

```bash
uvicorn app.main:app --host 0.0.0.0 --port 8000 --reload
```

The application is then available locally at:

```text
http://localhost:8000
```

---

## ☁️ Deployment

The application was previously deployed using **Railway** with a PostgreSQL database for demonstration purposes.

The free deployment period has expired, so the public demo is **currently offline**.

The repository remains fully available for:

* source-code review
* local deployment
* security testing
* architectural study
* portfolio demonstration

The project includes the required deployment configuration through the `Procfile`.

Example:

```text
web: uvicorn app.main:app --host 0.0.0.0 --port $PORT
```

---

## 🔐 Security Best Practices Applied

### Application

* RBAC for sensitive routes
* Segregation of Duties
* Password hashing with Bcrypt
* Session-based authentication
* Input validation
* Security event logging
* Automated account locking
* Restricted access to sensitive reports

### Security Monitoring

* Centralized security events
* Severity classification
* Persistent alert history
* Real-time WebSocket notifications
* Detection thresholds
* SOC-oriented dashboard
* Incident resolution workflow

### Development

Sensitive configuration is stored through environment variables.

```text
.env
```

must never be committed to the repository.

---

## 📈 Project Highlights

| Area           | Implementation                        |
| -------------- | ------------------------------------- |
| Authentication | Session-based authentication + Bcrypt |
| Authorization  | Role-Based Access Control             |
| Security model | Segregation of Duties                 |
| Monitoring     | Real-time SOC dashboard               |
| Detection      | 7 security detection rules            |
| Alerting       | LOW / MEDIUM / HIGH / CRITICAL        |
| Response       | Automatic account locking             |
| Real-time      | Native WebSockets                     |
| Persistence    | PostgreSQL                            |
| Logging        | File + database                       |
| Reporting      | Classification-aware PDF reports      |
| Architecture   | Layered + event-driven                |
| Deployment     | Railway + local                       |

---

## 🔮 Future Improvements

* [ ] TOTP-based 2FA
* [ ] IP-based rate limiting
* [ ] Email notifications for CRITICAL alerts
* [ ] Advanced security-event search
* [ ] CSV transaction export
* [ ] Complete audit trail
* [ ] Transaction history encryption
* [ ] Mandatory MFA for SOC accounts
* [ ] Machine-learning-based anomaly detection
* [ ] External REST API
* [ ] Improved incident-response workflows
* [ ] Centralized log management
* [ ] Integration with an external SIEM
* [ ] WAF integration
* [ ] IDS/IPS integration
* [ ] Production-grade deployment architecture

---

## 📄 License

This project was developed for academic and educational purposes.

Commercial use or reuse of the project should be subject to appropriate authorization.

---

<p align="center">
  <b>Xud-Bank — SecureDataMonitor</b><br>
  Secure Web Application · Event-Driven Security Monitoring · Real-Time SOC
</p>
