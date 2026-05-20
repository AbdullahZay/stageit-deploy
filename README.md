# StageIt

> A platform where game developers showcase their games and gamers discover hidden gems — giving every indie creator a stage, no matter how unknown.

---

## Overview

**StageIt** is a full-stack web platform built for game developers to share their games with the world — and for gamers to discover new titles from creators who haven't yet hit the spotlight. The goal is simple: give every developer a stage, so a talented but unknown creator with a great game can finally be seen.

The project is built with a **Spring Boot** backend, a **React + Vite** frontend, and a **PostgreSQL** database — all containerized with **Docker** for easy, reproducible deployment.

This repository (`stageit-deploy`) ties the backend and frontend repositories together using Git submodules and orchestrates them with Docker Compose, so the entire stack can be launched on any machine with a single command.

---

## Features

- **Create post** — Developer can publish his game image eith th game category and description
- **Comment** — Any logged In user can comment to the posts
- **Game Discovery** — Gamers can browse and explore games from creators by category on main menu even without log in.
- **Secure Authentication** — JWT-based registration and login for developers and gamers
- **User Profiles** — Personal profiles for users
- **RESTful API** — Clean, well-structured REST endpoints between frontend and backend
- **Single-Page Application** — Smooth client-side navigation via React Router
- **Persistent Storage** — Reliable data persistence with PostgreSQL
- **Modern Responsive UI** — Built with React 19 and Vite for fast performance

> For the full list of implemented features, in-progress tasks, and upcoming work, check the **Kanban boards** on the backend and frontend repositories linked at the bottom of this README.

---

## Tech Stack

### Backend

- **Java 21**
- **Spring Boot 3.5.14**
- **Spring Security**
- **Spring Data JPA**
- **JJWT 0.12.6**
- **Hibernate**
- **PostgreSQL**
- **Lombok**
- **Maven**

### Frontend

- **React 19**
- **Vite 8**
- **React Router DOM 7**
- **JavaScript (ES6+)**
- **CSS3**
- **ESLint**


---

## How to Run with Docker Compose

### Quick Start

Clone the repository (with submodules) and start the entire stack with one command:

```bash
git clone --recurse-submodules https://github.com/AbdullahZay/stageit-deploy.git
cd stageit-deploy
docker compose up --build
```

Once the build completes, open in your browser:

- **Frontend:** [http://localhost:3000](http://localhost:3000)
- **Backend API:** [http://localhost:8080](http://localhost:8080)
- **PostgreSQL:** `localhost:5432` (user: `stageit`, password: `stageitpass`, db: `stageit`)

### If You Forgot `--recurse-submodules` While Cloning

```bash
git submodule update --init --recursive
```

---

## Architecture

The codebase is organized into clear, separated modules:

- `stageit-frontend/src/pages/` holds React screen components
- `stageit-frontend/src/components/` holds reusable UI components
- `stageit-backend/.../controller/` holds REST endpoints
- `stageit-backend/.../service/` holds business logic
- `stageit-backend/.../repository/` holds data access layers
- `stageit-backend/.../config/` holds security and cross-cutting setup

---

## Design Patterns

The backend applies four classic design patterns to keep the codebase clean and extensible:

- **Builder** — Constructs complex objects step-by-step via Lombok's `@Builder`.
- **Singleton** — Ensures one shared instance per Spring-managed bean.
- **Facade** — Service layer hides business logic behind simple methods.
- **Chain of Responsibility** — Spring Security filters process requests sequentially.

---

## Related Repositories

- **Backend:** [github.com/AbdullahZay/stageit-backend](https://github.com/AbdullahZay/stageit-backend)
- **Frontend:** [github.com/AbdullahZay/stageit-frontend](https://github.com/AbdullahZay/stageit-frontend)

Each repository maintains its own **GitHub Projects Kanban board** for tracking features, and ongoing development.

---

## Summary

**StageIt** is a full-stack web platform that gives indie game developers a stage to showcase their work and helps gamers discover hidden gems from creators who haven't yet hit the spotlight. The project demonstrates a complete production-grade architecture: 
a Spring Boot REST API secured with JWT and Spring Security, a React + Vite single-page application, and a PostgreSQL database — all orchestrated together with Docker Compose for one-command deployment.

The backend is built around four key **design patterns** — **Builder**, **Singleton**, **Facade**, and **Chain of Responsibility** — ensuring the code stays clean, modular, and easy to extend. The use of Git submodules allows the backend and frontend to remain independent repositories with their own version histories and Kanban boards, while still being deployable together as a unified system.

Whether you're a developer looking to share your next game or a gamer searching for the next underrated title, **StageIt** is built to put creators and players on the same stage.

