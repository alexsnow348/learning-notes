# FastAPI Microservices
---

## Setup and required library

- Programming Language: Python
- Database Migrations: SQLAlchemy Alembic
- Database Model: SQLAlchemy
- Request and Response schemas: Pydanytic


## Migrate database with Alembic

- Step 1: Initialise the alembic file

```bash
alembic init <name-of-migrations-folder>
```

- Step 2: Edit `env.py`, file for `alembic.ini` file for required changes.

```
# uncomment the line for sqlalchemy.url from alembic.ini file
# sqlalchemy.url = driver://user:pass@localhost/dbname
```

```python

```