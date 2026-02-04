# Case 03: Data Center (HPC Infrastructure Digital Twin)

> [!WARNING]
> **Work in Progress:** This project is currently under active development. Some links and assets may be placeholders.

---

> **Role:** L1 Digital Twin (Infrastructure Monitoring)
> **Stack:** Houdini, Omniverse (USD/Python), MDL, Jira Integration

---

## 📋 Project Overview

This repository showcases a prototype **AI Inference Refinery (Level L1 Digital Twin)** demonstrating the visualisation of high-performance computing infrastructure within the Armenian tech ecosystem. The case study focuses on an **Inference Farm** hosting NVIDIA's **Nemotron-3** flagship models.

**Key Use Case:**
The digital twin visualises a **"Viral Inference Surge"** — a sudden spike in global requests. The scenario demonstrates the **sequential activation of 160 nodes** as the load balancer scales resources in real-time. Temperature escalation, airflow dynamics, and distributed data flows (RDMA) drive real-time heatmap shaders and HUD/FUI overlays.

**Project Focus:**

- **Photorealistic SimReady Assets:** Industry-standard asset quality for professional visualisation
- **Massive Scene Optimisation:** Point Instancing strategy rendering 10,000+ server units in real-time
- **MDL-Driven Visualisation:** Custom shaders binding thermal/power data directly to material properties

---

## 🎯 Technical Highlights

*This setup demonstrates an **L1 Digital Twin**, focusing on the visualization of critical infrastructure parameters (Thermal, Power, Network).*

- **Hero Asset**: **Blackwell Rig v1.0** (4U custom nodes featuring SilverStone RM44 chassis and 3x RTX PRO 4500 Blackwell GPUs).
- **Houdini "Refinery"**: Procedural rack generation and cascading airflow/thermal simulation prep.
- **USD Architecture**: Point Instancing strategy rendering **480 GPUs** across 16 racks in real-time.
- **MDL Visualization**: Custom shaders driving heatmaps and RDMA data-flow "pulses" directly from USD attributes.

## 👁️ Visual Proof

> *Placeholders for future GIFs - Replace with actual optimised media*

1. **Thermal Heatmap:** `![Heatmap Demo](docs/img/heatmap_demo.gif)`
2. **USD Composition:** `![Graph](docs/img/composition_graph.png)`
3. **Houdini PDG:** `![PDG Flow](docs/img/houdini_pdg.png)`

## 🏗️ Architecture & Decisions

This project follows a **README-driven structure** to manage the complexity of hybrid Houdini/Omniverse pipelines.

- [**View Architecture Decision Records (ADR)**](docs/adr/) – Design notes on Naming Conventions, Security Guardrails, and Dependency Locking.

## 📂 Repository Structure

```text
.
├── assets/
│   ├── _external/   # [DOWNLOADED] Runtime Assets (USD, Textures, HDRI) - Git Ignored
│   │   ├── usd/
│   │   ├── tex/
│   │   └── hdri/
│   └── local/       # Lightweight assets tracked by Git
├── docs/        # ADRs and knowledge base
│   ├── plans/   # Implementation plans & tech debt
├── src/         # Core logic and scripts
├── tests/       # Validation and testing suite
└── tools/       # Internal pipeline utilities
```

- [**View Composition Graph**](docs/composition_graph.mermaid) – Visual breakdown of the USD layering strategy.

---

## 💾 Project Data / Assets

### 🏭 The "Factory" Narrative
>
> This repository follows a strict **"Source vs. Artifact"** philosophy:
>
> - **Houdini (Fabricator):** The procedural "factory" where assets are generated. Source files (`.hip`) are proprietary and **excluded** from this repository.
> - **USD (Artifact):** The "product" of the factory. These are the optimized files needed to run the Digital Twin in Omniverse.
> - **Synthetic Data:** Telemetry streams are emulated via Python generators to simulate robust edge cases (e.g., extreme thermal loads) that are rarely captured in real-world data.

### 📦 Asset Hydration

To keep this repository lightweight, heavy binary assets (USD Crates, Textures, HDRIs) are stored externally.

- [**Download Asset Pack (One Drive / S3 Link TBD)**](https://example.com/placeholder)

**Hydration Steps:**

1. Download the ZIP archive from the link above.
2. **Extract contents** directly into the `assets/_external/` folder.
    - *Note: This folder already exists (anchored by `.gitkeep`), so you simply unzip into it.*
    - *Result:* Your local path should look like `assets/_external/usd/my_asset.usd`.

## 🛠️ Setup & Installation

1. **Clone:** `git clone https://github.com/MSP014/dt-openusd-showcase-case03-dc.git`
2. **Hydration:** (See "Asset Hydration" above) - Extract assets to `assets/_external/`.
3. **Env:** Create conda env: `conda create -n case03-env python=3.10`
4. **Deps:** `pip install -r requirements.txt`
5. **Hooks:** `pre-commit install`

---

## 📜 Changelog

- **2026-02-02:** Implemented external storage strategy for heavy assets (Git-agnostic).
- **2026-01-22:** Initial repository bootstrap. Established **Nvidia Showreel Protocol** (ADRs, Pre-commit, Hybrid Access).
