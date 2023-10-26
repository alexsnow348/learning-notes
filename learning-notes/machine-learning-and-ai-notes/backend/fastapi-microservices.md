# FastAPI Microservices
---

## Setup and required library


|  Required |  Tools Used |
|:--------- |:-----------|
|Programming Language| Python|
|Database Migrations| SQLAlchemy Alembic|
|Database Model| SQLAlchemy|
|Request and Response schemas | Pydanytic |
| Package manager| Poetry|



## Migrate database with Alembic


![[alembic-sql-migration.png]]

- Step 1: Initialise the alembic file

```bash
alembic init <name-of-migrations-folder>
```

- Step 2: Edit `alembic.ini` file for required changes.

```
# uncomment the line for sqlalchemy.url from alembic.ini file
# sqlalchemy.url = driver://user:pass@localhost/dbname
```

- Step 3: Edit `env.py` for `target_metadata` change and `sqlalchemy.url` changes.

```python
...
# update the target_metatdata to current app Base metatdata
from app.db.database import Base
target_metadata = Base.metadata

# generate db_url string based on os config
def get_db_url() -> str:
	username = os.getenv("POSTGRES_USER", "postgres")
	password = os.getenv("POSTGRES_PASSWORD", "postgres")
	host = os.getenv("POSTGRES_HOST", "db")
	port = os.getenv("POSTGRES_PORT", "5432")
	database = os.getenv("POSTGRES_DB", "postgres")
	return f"postgresql://{username}:{password}@{host}:{port}/{database}"

...

# reset the configuration to use updated db_url 
configuration = config.get_section(config.config_ini_section)
configuration["sqlalchemy.url"] = get_db_url()

```

- Step 4: Generate initial migration files .

```bash
# manual
alembic revision -m "<name-of-migration-changes-make>"

# autogenerate
alembic revision --autogenerate -m "<name-of-migration-changes-make>"
```
