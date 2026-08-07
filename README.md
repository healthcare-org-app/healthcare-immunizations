# immunizations-service

immunizations-service — domain: ehr

- **Port:** 8306
- **Language:** Python 3.11 + Flask
- **Database:** `ehr` (Postgres, table `immunizations`)
- **Event bus:** Kafka

## API

| Method    | Path                       |
|-----------|----------------------------|
| GET       | `/api/immunizations/`          |
| POST      | `/api/immunizations/`          |
| GET       | `/api/immunizations/<id>`      |
| PUT/PATCH | `/api/immunizations/<id>`      |
| DELETE    | `/api/immunizations/<id>`      |
| GET       | `/health`                  |
| GET       | `/ready`                   |

## Events

**Publishes:** (none)
**Subscribes:** (none)

## HTTP peer dependencies

- `patients-service`
- `audit-log-service`

## Local dev

```bash
pip install -e ../../libs/py-healthcare-common
pip install -r requirements.txt
cp .env.example .env
(cd ../../infra && docker compose up -d postgres kafka kafka-init)
python -m app.main
```

## Tests

```bash
pytest
```
