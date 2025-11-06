# 360° Adaptive Streaming with Language-Guided Semantic Priors

This repository contains the source code for a 6-week undergraduate research project to build and evaluate a novel 360° adaptive streaming client. The system leverages edge-offloaded semantic priors, lightweight on-device personalization, and a contextual bandit controller to optimize the trade-off between Quality of Experience (QoE) and on-device energy consumption.

---

### Key System Components
-   **Edge Semantic Priors:** Offline generation of K-class semantic tile maps from video content.
-   **On-Device Personalization:** Learns a per-user preference vector `w` over semantic classes.
-   **Cross-Modal FoV Predictor:** A tiny Transformer model that fuses head motion and semantic priors.
-   **Contextual Bandit Controller:** Dynamically adapts update rates, offloading, and saccade-gating.
-   **Two-Stage ABR:** A prefetch/enhance scheduler based on a Multiple-Choice Knapsack Problem (MCKP).

---

### Directory Structure
```
.
├── data/              # Placeholder for datasets (ignored by git)
├── docs/              # Project reports, diagrams, and final presentation
├── notebooks/         # Jupyter notebooks for exploration and analysis
├── scripts/           # Standalone scripts (data processing, experiment runners)
├── src/               # Main source code
│   ├── abr/           # ABR and tile scheduling logic (MCKP)
│   ├── bandit/        # Contextual bandit controller
│   ├── common/        # Shared utilities (logger, tiling geometry)
│   ├── personalize/   # Personalization head training and fusion
│   ├── predictor/     # FoV prediction model
│   └── semantics/     # Semantic prior generation
├── tests/             # Unit tests for key components
├── .gitignore         # Files and directories ignored by git
├── main.py            # Main simulation entry point
├── README.md          # This file
└── requirements.txt   # Python project dependencies
```

---

### Getting Started

1.  **Clone the repository:**
    ```bash
    git clone <your-repository-url>
    cd 360-streaming-semantics-project
    ```

2.  **Create a Python virtual environment:**
    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
    ```

3.  **Install the required dependencies:**
    ```bash
    pip install -r requirements.txt
    ```

### How to Run the Simulation

Execute the main simulation script from the root of the project directory:

```bash
python main.py --mode proposed --user U01 --video V01 --network-trace traces/trace1.json
```
