# Data Engineering Pipeline — Airflow, dbt, Soda & BigQuery

An end-to-end data engineering project that loads retail data into BigQuery, applies transformations with dbt, and validates data quality using Soda — all orchestrated through Apache Airflow.

---

## Project Structure

| Path | Purpose |
|---|---|
| `dags/` | Airflow DAGs — includes the `retail` DAG covering ingestion through visualization |
| `include/` | Supporting project files |
| `plugins/` | Custom or community Airflow plugins |
| `Dockerfile` | Versioned Astro Runtime image |
| `packages.txt` | OS-level dependencies |
| `requirements.txt` | Python dependencies |
| `airflow_settings.yaml` | Local Airflow connections, variables, and pools |

---

## Running Locally

**1. Start the project**
```bash
astro dev start
```

This spins up 4 Docker containers:

- **Postgres** — Airflow metadata database
- **Webserver** — Airflow UI
- **Scheduler** — monitors and triggers tasks
- **Triggerer** — handles deferred tasks

**2. Confirm containers are running**
```bash
docker ps
```

**3. Open the Airflow UI**

Navigate to [http://localhost:8080](http://localhost:8080) and log in with `admin` / `admin`.

> Postgres is available at `localhost:5432/postgres`. If ports `8080` or `5432` are already in use, stop the conflicting containers or update the port configuration.

---

## Deploying to Astronomer
```bash
astro deploy
```

Full instructions: [docs.astronomer.io/cloud/deploy-code](https://docs.astronomer.io/cloud/deploy-code/)
