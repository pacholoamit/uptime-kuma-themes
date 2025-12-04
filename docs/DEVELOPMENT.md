# Development

This guide covers setting up and running the development environment for Uptime Kuma Themes.

## Prerequisites

- [Bun](https://bun.sh/) (v1.0+)
- [Docker](https://www.docker.com/) and Docker Compose

## Quick Start

```bash
# Clone the repository
git clone https://github.com/pacholoamit/uptime-kuma-themes.git
cd uptime-kuma-themes

# Install dependencies
bun install

# Start development environment (Uptime Kuma + Mock Server)
bun dev

# Seed the database with mock monitors
bun run db:seed
```

This will start:
- **Uptime Kuma** at http://localhost:3001
- **Mock Server** at http://localhost:3000

## Default Credentials

| Field | Value |
|-------|-------|
| Username | `user` |
| Password | `password123` |

## Available Scripts

```bash
# Start mock server only
bun run server

# Start mock server with hot reload
bun run server:dev

# Start Uptime Kuma (Docker)
bun run docker:up

# Stop Uptime Kuma
bun run docker:down

# Start everything for development
bun dev

# Seed database with monitors for mock endpoints
bun run db:seed

# Force re-seed (clears existing mock monitors first)
bun run db:seed:force
```

## Mock Server Endpoints

The mock server provides various endpoints to test different monitoring scenarios:

### Always States
- `GET /always-up` - Always returns 200 OK
- `GET /always-down` - Always returns 500 error

### Failure Patterns
- `GET /random-failures` - 20% chance of failure
- `GET /frequent-failures` - 50% chance of failure
- `GET /intermittent` - Fails every 3rd request
- `GET /flapping` - Alternates between up and down

### Timing Issues
- `GET /slow-response` - 2-5 second delay
- `GET /very-slow` - 10-15 second delay
- `GET /timeout` - Never responds
- `GET /memory-leak` - Gets slower with each request

### Status Variations
- `GET /degraded` - Returns 200 with degraded status
- `GET /maintenance` - Returns 503 Service Unavailable
- `GET /scheduled-down` - Down during minutes 0-5 and 30-35
- `GET /partial-outage` - Random partial service outage
- `GET /rate-limited` - Returns 429 after 10 req/min

### Health Checks
- `GET /health` - Detailed health check response
- `GET /ping` - Simple ping/pong
- `GET /keyword-check` - JSON with monitorable keywords
- `GET /html-status` - HTML page with status
- `GET /cert-check` - Certificate expiry simulation
- `GET /status/:code` - Returns specified HTTP status code

### Docker Simulation
- `GET /docker/healthy` - Healthy container status
- `GET /docker/unhealthy` - Unhealthy container status

## Connecting Uptime Kuma to Mock Server

Since Uptime Kuma runs in Docker, use `host.docker.internal` to reach the mock server:

```
http://host.docker.internal:3000/always-up
```

## Project Structure

```
uptime-kuma-themes/
├── themes/                    # CSS theme files
│   ├── gruvbox/
│   │   ├── index.css
│   │   └── default.png
│   ├── catppuccin/
│   └── .../
├── layouts/                   # CSS layout files
│   ├── compact/
│   ├── two-column/
│   └── .../
├── server/
│   └── index.ts               # Mock server for testing
├── migrations/
│   └── 001_seed_monitors.ts   # Database seeder for mock endpoints
├── docs/
│   ├── CONTRIBUTING.md
│   └── DEVELOPMENT.md
├── data/                      # Uptime Kuma data (gitignored)
├── docker-compose.yml
├── package.json
└── README.md
```

## Database Migrations

The project uses Bun's native SQLite module for database operations.

### Seeding Monitors

The migration script `migrations/001_seed_monitors.ts` creates monitors for all mock server endpoints:

```bash
# Seed monitors (skips existing)
bun run db:seed

# Force re-seed (clears and recreates all mock monitors)
bun run db:seed:force
```

### Creating New Migrations

To add new migrations:

1. Create a new file in `migrations/` with the naming convention `XXX_description.ts`
2. Use Bun's `bun:sqlite` module for database operations
3. Add a corresponding script to `package.json` if needed

## Troubleshooting

### Uptime Kuma not starting

```bash
# Check if Docker is running
docker ps

# View Uptime Kuma logs
docker compose logs uptime-kuma

# Restart the container
bun run docker:down && bun run docker:up
```

### Mock server connection issues

Ensure you're using `host.docker.internal:3000` (not `localhost:3000`) when configuring monitors in Uptime Kuma.

### Database issues

```bash
# Reset the database by removing the data directory
rm -rf data/
bun run docker:up  # This will recreate the database
bun run db:seed    # Re-seed the monitors
```

### Port conflicts

If port 3000 or 3001 is already in use:

```bash
# Find processes using the ports
lsof -i :3000
lsof -i :3001

# Kill the processes or change the ports in docker-compose.yml and server/index.ts
```
