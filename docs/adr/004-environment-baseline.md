# ADR 004: Environment Baseline

## Status

Accepted

## Context

Different Python versions introduce subtle incompatibilities in libraries like `usd-core`, `pandas`, or `numpy`. To ensure the "NVIDIA Showreel Standard" is maintainable, we must lock the Python version across the estate.

## Decision

We anchor all Case 03 environments on a specific Python baseline:

### 1. Python Version

* **Baseline**: **Python 3.10.x** (specifically 3.10.12+).
* **Rationale**: This version provides the best stability for current NVIDIA Omniverse Kit extensions and SideFX Houdini (20.x+) Python 3 builds.

### 2. Base Configuration

* **Package Manager**: `conda` (Miniconda/Anaconda) for environment creation.
* **Installer**: `pip` (latest) for package installation within the activated conda environment.

## Consequences

* **Positive**: Minimises "syntax error" or "library not found" issues during cross-case development.
* **Negative**: Requires reinstalling environments if they were built on 3.11+ or 3.9-.
