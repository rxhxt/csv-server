# Contributing to CSV Server

Thank you for your interest in contributing to **CSV Server**!  
We welcome bug reports, feature requests, documentation improvements, and code contributions.

---

## How to Contribute

### 1. Fork the Repository

Click the **Fork** button at the top right of the [GitHub repo](https://github.com/yourusername/csv-server) and clone your fork:

```bash
git clone https://github.com/yourusername/csv-server.git
cd csv-server
```

### 2. Set Up Your Development Environment

We recommend using a virtual environment:

```bash
python -m venv venv
source venv/bin/activate
pip install -e .[dev]
```

### 3. Create a Branch

Create a new branch for your feature or fix:

```bash
git checkout -b my-feature
```

### 4. Make Your Changes

- Follow [PEP 8](https://www.python.org/dev/peps/pep-0008/) style guidelines.
- Write clear commit messages.
- Add or update tests as appropriate.

### 5. Run Tests and Linters

Before submitting, ensure all tests pass and code is formatted:

```bash
pytest
black .
flake8 .
```

### 6. Submit a Pull Request

Push your branch and open a pull request on GitHub.  
Describe your changes and reference any related issues.

---

## Reporting Issues

If you find a bug or have a feature request, please [open an issue](https://github.com/yourusername/csv-server/issues) and provide as much detail as possible.

---

## Need Help?

If you have questions, open an issue or start a discussion on GitHub.

---

Thank you for helping make CSV Server better!