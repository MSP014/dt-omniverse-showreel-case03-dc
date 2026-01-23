# ADR 002: QA & Security Protocols

## Status

Accepted

## Context

For an Infrastructure Digital Twin (Data Center), data fidelity is paramount. We need to respect the integrity of the simulation code and prevent leakage of server configurations or DB access strings.

## Decision

We enforce a strict "Shift Left" strategy using `pre-commit` hooks and automated guardrails:

### 1. Guardrails (Pre-commit)

* **Linting:** `black` (Formatting), `flake8` (Logic), `isort` (Imports).
* **Security:**
  * `bandit`: Scans for common security issues (e.g., hardcoded credentials in connection scripts).
  * `pip-audit`: Checks `requirements.txt` for known vulnerabilities.
* **Hygiene:** `check-added-large-files` (Max 10MB) to prevent repo bloating.

### 2. Testing

* `pytest` must pass locally before push.
* **Data Validation:** Tests MUST verify that generated JSON thermal data matches the expected schema for the MDL sensors.
* **Note:** Tests are covered by Linters (Black/Flake8) but excluded from Bandit security scans to avoid false positives related to `assert` usage.

### 3. Secrets Management

* **Isolation**: All sensitive data (DB credentials, sensor API keys) MUST be stored in a `.env` file.
* **Sanity**: The `.env` file MUST be included in `.gitignore`. Never commit secrets to version control.

## Consequences

* **Positive:** Higher code quality, reduced security risk, blocked accidental large files.
* **Negative:** Initial setup friction; `pip-audit` requires maintenance of `requirements.txt`.
