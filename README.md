# Task-6: Professional Dockerized Strapi Environment

## 1. Project Overview
This project focuses on containerizing a **Strapi CMS** application to ensure a consistent development and production environment. The architecture includes a **PostgreSQL** database for data persistence and an **Nginx** reverse proxy for secure traffic management and WebSocket handling.



---

## 2. Technical Architecture
* **Application Layer**: Strapi Headless CMS running on Node.js.
* **Database Layer**: PostgreSQL 16 (Alpine) with persistent volume mapping to `strapi-db-data`.
* **Proxy Layer**: Nginx serving as a reverse proxy on Port 80, configured to handle internal Port 1337 traffic.

---

## 3. Key Challenges & Technical Fixes

### A. Nginx WebSocket Resolution
During deployment, a `404 Not Found` error was identified on the `/ws` (WebSocket) endpoint.
* **Solution**: Updated the Nginx `default.conf` to include `Upgrade` and `Connection` headers to facilitate the HTTP/1.1 handshake required for WebSockets.



### B. Professional Git Workflow
* **Branching Strategy**: All development was performed on the feature branch `nithin-task-6-dockerized`.
* **Conflict Management**: Resolved a complex **Merge Conflict** in the `README.md` using the Git Merge Editor to ensure local changes integrated with the organization's main history.
* **History Syncing**: Utilized the `--allow-unrelated-histories` flag to successfully pull and push code across divergent commit histories.

---

## 4. Core Commands Used

| Category | Command | Purpose |
| :--- | :--- | :--- |
| **Docker** | `docker-compose up -d` | Start services in detached mode |
| **Docker** | `docker-compose down` | Stop and remove containers |
| **Git** | `git init` | Initialize project repository |
| **Git** | `git pull origin main` | Sync with organization repository |
| **Git** | `git push origin [branch]` | Upload code for PR creation |

---

## 5. Project Structure
```text
TASK-6-DOCKERIZED/
├── nginx/
│   └── default.conf      # Nginx Proxy Configuration
├── docker-compose.yml    # Container Orchestration
├── .env                  # Environment Variables
└── README.md             # Documentation

Prepared by: Nithin Settibathula
