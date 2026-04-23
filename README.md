# tce_tfi_abm
Agent-based model of tumor–T cell interactions to evaluate treatment-free interval (TFI) schedules in CD19×CD3 T cell engager therapy.

How to Run
Requirements
Java 1.8+
Hybrid Automata Library (HAL)

Output
CSV files with:
tumor counts
T cell populations
exhaustion levels
Optional visualization (toggle VISUALS = true in code)

Reproducibility
Each condition simulated with 50 independent runs
Fixed random seeds per run
Output stored as CSV for downstream analysis

Notes and Assumptions
PD-1 represents a composite exhaustion index
Tumor cells are non-motile (pre-irradiated in vitro assumption)
TCE exposure is modeled as a binary on/off variable with decay-based reversion
Spatial interactions are limited to Moore neighborhood

Model Summary
2D lattice 
Initial E:T ratio = 1:4 (20% T cells, 80% tumor cells)
Time step = 1 hour
Agents:
Tumor cells 
CD8⁺ T cells:
inactive
active (cytotoxic)
exhausted

Key modeled processes:

Contact-dependent tumor killing
T cell proliferation with resource limitation
PD-1–based exhaustion driven by cumulative tumor killing events (higher under TCE exposure), with probabilistic transition to exhaustion once a threshold is reached (composite exhaustion index).
TCE-dependent activation and exhaustion dynamics of T cells
Treatment-free interval (TFI) scheduling of T cell engager (TCE)
