# Symfony skeleton with PHP 8.5 Runtime

### Tech Stack

- **Backend:** PHP 8.5 / Symfony 8.0 (served via nginx + php-fpm)

### Quality Gates

**Backend (PHP):**
- `docker/phpunit` -- PHPUnit tests (unit, integration, functional)
- `docker/phpstan` analyse -- PHPStan static analysis (level 5)
- `docker/php-cs-fixer` fix --dry-run -- PHP CS Fixer code style

### Docker Setup

All services run in Docker. The `docker/` directory contains shortcut scripts:

| Script | Description |
|--------|-------------|
| `docker/shell` | Open a bash shell in the php-fpm container |
| `docker/composer` | Run Composer commands |
| `docker/phpstan` | Run PHPStan |
| `docker/php-cs-fixer` | Run PHP CS Fixer |
| `docker/phpunit` | Run PHPUnit |

### Services & Ports

| Service | Container | Port |
|---------|-----------|------|
| Nginx (API) | skeleton-webserver | 57123 |

### Getting Started

```bash
# Start all containers
docker compose up -d

# Install backend deps
docker/composer install

# Run backend tests
docker/phpunit
```
