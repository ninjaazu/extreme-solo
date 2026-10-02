# AGENTS.md

## Project Overview
Single static HTML page (`index.html`) — "Extreme Solo", a hub of Roblox scripts/executor links. No build tools, no backend, no dependencies, no package manager.

## Running the app
- Served via `docker-compose.base44.yml` using `python:3.12-slim` running `http.server` on port 80 (host port 3000).
- The sandbox directory has restrictive permissions (700, root-only); nginx workers cannot traverse it, so Python's `http.server` (runs as root) is used instead.
- The source directory is bind-mounted read-only, so edits to `index.html` are reflected immediately on browser refresh.

## No secrets required
The app is fully static with no external service dependencies.
