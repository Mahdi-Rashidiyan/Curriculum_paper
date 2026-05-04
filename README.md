# Curriculum Learning Can Irreversibly Harm Generalization
## NeurIPS 2026 – Supplementary Material

This repository contains all code and data to reproduce the experiments described in the paper. The entire pipeline runs on a single laptop with **4 GB VRAM** and completes in **less than one hour**.

---

## 1. Requirements

- Python 3.8+
- NumPy
- PyTorch (CPU or GPU)
- Matplotlib

Install with:

```bash
pip install numpy torch matplotlib

# 1. Generate the training and test datasets (seconds)
python generate_data.py

# 2. Train the baseline MLP and save a checkpoint (seconds)
python train_baseline.py

# 3. Run the full phase‑diagram sweep (450 models, ≈10 minutes)
python run_sweep.py

# 4. Causal intervention: capacity boost (≈2 minutes)
python boost_experiment.py

# 5. Causal intervention: curriculum reversal (≈2 minutes)
python curriculum_reversal.py

# 6. Architectural comparison on CNN (≈2 minutes)
python cnn_experiment.py

# 7. Architectural comparison on Transformer (≈2 minutes)
python transformer_experiment.py

# 8. Architectural comparison on RL agent (≈5 minutes)
python rl_experiment.py

# 9. Mechanistic analysis (gradient dynamics, representation collapse) (≈5 minutes)
python gradient_analysis.py
python gradient_dynamics.py
python representation_analysis.py

# 10. Mechanistic triple (MLP, CNN, Transformer) (≈5 minutes)
python mechanistic_triple.py

# 11. Generate the phase‑diagram and heatmap figures (seconds)
python plot_results.py