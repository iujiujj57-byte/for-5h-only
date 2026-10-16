# AGENTS.md

## Project Overview
NexPlay is a static HTML/CSS game hub website. No build tools, no framework, no package manager.

## Setup
- Served by nginx (alpine) via `docker-compose.base44.yml`
- Static files are bind-mounted from the repo root into `/usr/share/nginx/html`
- `main.html` is served as the index page (configured in `nginx.base44.conf`)
- Web entry point: host port 3000 → nginx port 80

## Running
```
docker compose -f docker-compose.base44.yml up -d
```

## Notes
- The repo root directory needs `chmod 755` so nginx's worker process can read the bind-mounted files.
- No external credentials or secrets required.
- Changes to `main.html` or `style.css` are immediately reflected (just refresh the browser).
