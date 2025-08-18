# CSV Server

This project implements a CSV Server, a Python library and CLI that turns CSV files into REST APIs, similar to json-server but specifically for CSV files. 

## Goals

- **Drop-in Tool**: Point to a folder of .csv files and instantly get REST endpoints.
- **Read-only Default**: The server operates in read-only mode by default, with optional safe writes (POST/PUT/PATCH/DELETE).
- **Auto ID Support**: Automatically synthesize and increment an ID if CSVs do not have a primary key.
- **Query Parameters**: Support for searching, filtering, sorting, and pagination.
- **Safe Writes**: Ensure atomic replace operations with file locks.
- **Swagger Documentation**: Interactive API documentation available at `/docs`.

## Tech Stack

- **FastAPI**: Web framework with automatic OpenAPI documentation.
- **Typer**: Command Line Interface (CLI) framework.
- **portalocker**: Library for safe file locks.
- **csv**: Standard library for parsing and writing CSV files.
- **pandas**: Optional library for handling large datasets.
- **pytest + httpx**: Testing framework and HTTP client for tests.
- **ruff, mypy**: Tools for linting and type checking.

## Directory Layout

```
csv_server/
  __init__.py
  cli.py
  app.py
  resources.py
  config.py
  storage/
    base.py
    csv_store.py
    sqlite_store.py (optional)
  query.py
  utils_csv_ids.py
  version.py
tests/
examples/
  data/users.csv
  data/orders.csv
  config.yaml
pyproject.toml
README.md
LICENSE
```

## Core Features

- **GET /users**: List rows with support for query parameters like `q`, `filter`, `sort`, `limit`, and `offset`.
- **GET /users/{id}**: Fetch a single row by ID.
- **POST /users**: Add a new row with auto-assigned ID if missing.
- **PUT/PATCH /users/{id}**: Update or replace a row.
- **DELETE /users/{id}**: Delete a row.
- **ETags + If-None-Match**: Support for 304 Not Modified responses.
- **OpenAPI Documentation**: Available at `/docs`.

## Auto-ID Handling

The server automatically manages primary keys and ID assignments, ensuring that each entry in the CSV files has a unique identifier.

## CLI

The server can be run using Typer with commands to specify the directory of CSV files and other options, such as read-only mode.

## Configuration

The server supports a YAML configuration file to manage settings like server port, read-only mode, and resource definitions.

## Testing

The project includes tests using pytest and httpx to ensure that all features work as expected, including handling of query parameters and safe writes.

## Example Data

Example CSV files are provided in the `examples/data/` directory for demonstration purposes.

## Roadmap

Future enhancements include:
- Implementing an SQLite backend for larger datasets.
- Adding hot reload functionality for CSV files.
- Supporting relationships between resources.
- Creating Docker images for easy deployment.

## How to Contribute

Contributions are welcome! Please follow the guidelines in the repository for submitting issues and pull requests.

## License

This project is licensed under the MIT License. See the LICENSE file for more details.