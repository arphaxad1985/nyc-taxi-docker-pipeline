# NYC Taxi Data Pipeline — Dockerised Ingestion

A Dockerised data ingestion pipeline that loads NYC taxi trip data into PostgreSQL.

## What it does

1. Downloads NYC taxi trip data
2. Loads it into PostgreSQL (`ny_taxi` database, `yellow_taxi_trips` table)
3. Includes pgAdmin for visual database management

## Stack

- Python 3.13
- uv (dependency management)
- pandas, SQLAlchemy, psycopg2
- PostgreSQL 18
- pgAdmin 4
- Docker + Docker Compose

## Files

| File | Purpose |
|------|---------|
| `Dockerfile` | Builds the ingestion image (uv + ingest_data.py) |
| `pyproject.toml` | Python dependencies |
| `uv.lock` | Pinned versions (reproducible builds) |
| `ingest_data.py` | The ingestion script |
| `docker-compose.yaml` | Postgres + pgAdmin + ingestion service |

## How to run

### 1. Start the database and pgAdmin

```bash
docker compose up -d pgdatabase pgadmin