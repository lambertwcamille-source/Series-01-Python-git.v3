# Copilot Instructions for AI Agents

## Project Overview
This project is a minimal, reproducible template for data analysis in Python, focused on human movement science research. The workflow is notebook-driven, with all analysis and visualization performed in Jupyter notebooks for clarity and reproducibility.

## Key Files & Structure
- `Series01.ipynb.ipynb`: Main entry-point notebook. Orchestrates the workflow and can run other notebooks using `%run`.
- `notebooks/`: Contains modular analysis notebooks (e.g., `ecg_00.ipynb` for ECG data analysis).
- `data/`: Stores raw data files (e.g., `ECG_hz.txt`, `ECGu.txt`). See `data/readme.md` for file descriptions.
- `readme.md`: Project setup, usage, and high-level documentation.

## Patterns & Conventions
- **Notebook Path Handling**: Always set file paths relative to the project root to ensure compatibility when running notebooks directly or via `%run`. Example:
  ```python
  import os
  if os.getcwd().endswith("notebooks"):
      os.chdir("..")
  fNameECG = "data/ECG_hz.txt"
  ```
- **Data Loading**: Use `numpy.genfromtxt` with comma delimiter for reading data files.
- **Plotting**: Use `matplotlib.pyplot` for all visualizations.
- **No build/test scripts**: All work is performed interactively in notebooks; there are no Makefiles, test runners, or custom scripts.

## Developer Workflow
1. Open the project in VS Code or a Jupyter-compatible IDE.
2. Run `Series01.ipynb.ipynb` to execute the main workflow. This notebook may call others using `%run notebooks/other_notebook.ipynb`.
3. Add new analysis notebooks to `notebooks/` and reference them from the main notebook as needed.
4. Place new data files in `data/` and document them in `data/readme.md`.

## External Dependencies
- Minimal Python environment required. See `readme.md` for recommendations.
- Required packages: `numpy`, `matplotlib` (install via pip or conda).

## Example: Adding a New Analysis
1. Create a new notebook in `notebooks/` (e.g., `notebooks/my_analysis.ipynb`).
2. Use the path handling pattern above to access data files robustly.
3. Reference your notebook from `Series01.ipynb.ipynb` using `%run notebooks/my_analysis.ipynb`.

## AI Agent Guidance
- Always ensure file paths are robust for both direct and indirect notebook execution.
- Follow conventions for data loading and plotting as shown in existing notebooks.
- Update `readme.md` and `data/readme.md` when adding new files or workflows.
- Keep the project minimal, modular, and reproducible.
