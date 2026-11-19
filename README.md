# Folium

**A real-time collaborative note-taking system with a multithreaded C++ backend.**

Folium lets multiple users edit shared notes at the same time. The frontend is built in Svelte; the backend is a custom multithreaded C++ server on PostgreSQL, designed around safe concurrent access to shared documents.

## Features

- **Real-time shared editing** backed by ACID transactions and mutex-based synchronization
- **Dispatcher / thread-pool server** that routes requests to worker threads and enforces access control
- **Layered backend** with a data-access layer (DAL) and dispatcher kept as separate, modular components
- **JWT-based session management** for multi-user collaboration
- **Cloud deployment**: Vercel-hosted frontend talking to an AWS-hosted C++ backend

## Tech stack

| Layer | Technologies |
|---|---|
| Frontend | Svelte, JavaScript |
| Backend | C++ (multithreaded server), REST APIs, JWT |
| Data | PostgreSQL, MySQL |
| Deployment | Vercel, AWS |

## Architecture

```
Svelte client  ──REST/JWT──▶  Dispatcher ──▶ Thread pool ──▶ Data-access layer ──▶ PostgreSQL
```

## Author

Built by [Omar Ramadan](https://github.com/Omar1Ramadan).
