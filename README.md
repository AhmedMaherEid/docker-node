# 🚀 Node.js + PostgreSQL + Nginx (Dockerized App)

A fully containerized **Node.js** web application built with **Express**, **PostgreSQL**, and **Nginx**, orchestrated using **Docker Compose**.
This project demonstrates how to build a complete backend stack with isolated environments for the app, database, and reverse proxy.

---

## 🧱 Tech Stack

| Component             | Description                            |
| --------------------- | -------------------------------------- |
| **Node.js (Express)** | REST API server                        |
| **PostgreSQL**        | Database for persistent storage        |
| **Nginx**             | Reverse proxy & static request routing |
| **Docker Compose**    | Container orchestration & networking   |

---

## ⚙️ Features

* 🔁 **Hot reload** via `nodemon` for development mode
* 💾 **Persistent PostgreSQL** storage with Docker volumes
* 🌐 **Custom Nginx proxy** configuration for reverse routing
* 🧩 **Multi-container network** (`app-network`) for service isolation
* 🔐 **Environment variable management** via `.env` file
* 🪶 Lightweight and production-ready Docker setup

---

## 🗂️ Project Structure

```
node-app/
├── src/
│   ├── index.js
│   └── ...
├── nginx/
│   └── default.conf
├── Dockerfile
├── docker-compose.yml
├── docker-compose.dev.yml
├── .env
└── README.md
```

---

## ⚡ Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/<your-username>/node-app.git
cd node-app
```

### 2. Create an `.env` file

```bash
POSTGRES_USER=root
POSTGRES_PASSWORD=example
POSTGRES_DB=mydb
NODE_ENV=development
```

### 3. Start the containers

```bash
docker-compose -f docker-compose.yml -f docker-compose.dev.yml up --build
```

---

## 🌐 Access the Services

| Service         | URL                                            | Description                         |
| --------------- | ---------------------------------------------- | ----------------------------------- |
| **Express App** | [http://localhost:4000](http://localhost:4000) | Direct connection to Node.js server |
| **Nginx Proxy** | [http://localhost:8080](http://localhost:8080) | Routed through Nginx reverse proxy  |
| **PostgreSQL**  | `localhost:5432`                               | Database service                    |

---

## 🧰 Common Commands

| Action                         | Command                                                    |
| ------------------------------ | ---------------------------------------------------------- |
| View running containers        | `docker ps`                                                |
| Tail logs                      | `docker logs -f express-node-app-container`                |
| Access Node.js container shell | `docker exec -it express-node-app-container bash`          |
| Access PostgreSQL shell        | `docker exec -it node-app-postgres-1 psql -U root -d mydb` |
| Stop all containers            | `docker-compose down`                                      |

---

## 🧠 Key Concepts Learned

* File syncing with Docker using `nodemon` and `CHOKIDAR_USEPOLLING`
* Network communication between containers (`node-app ↔ postgres`)
* Using Nginx as a reverse proxy for containerized apps
* Debugging connection and environment issues in Docker

---

## 🪴 Future Improvements

* Add migrations with `Sequelize` or `Prisma`
* Implement a RESTful API with CRUD endpoints
* Add a frontend service (React/Vue) to complete the stack
* Configure production deployment workflow (e.g., Docker Swarm, ECS)

---

## 📜 License

MIT © 2025 Ahmed Maher
