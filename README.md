# TCAD Silicon Surrogate Tutorial

This teaching package contains a Jupyter notebook for a TCAD-to-AI workflow using Silicon MOSFET simulation data.

Students will:

1. Read Sentaurus Workbench metadata from `gtree.dat`.
2. Extract Id-Vg curves from `.plt` files.
3. Interpolate curves onto a common gate-voltage grid.
4. Cluster Id-Vg curves.
5. Extract `Ion`, `Ioff`, and `SS`.
6. Train surrogate models.
7. Use the surrogate model for multi-objective optimization.
8. Identify Pareto-optimal design candidates.

## Folder Structure

```text
TCAD_Silicon_Surrogate_Tutorial/
|-- tcad_silicon_surrogate_tutorial.ipynb
|-- requirements.txt
|-- README.md
|-- teaching_support/
|   |-- tcad_project_helpers.py
|-- data/
|   |-- raw_plt/
|       |-- README.md
|-- outputs/
|   |-- .gitkeep
```

## Data Placement

Before running the notebook, place the TCAD data files in:

```text
data/raw_plt/
```

The folder should contain:

```text
gtree.dat
IdVgsSat_n<node>_des.plt
```

The notebook will generate intermediate CSV files and final outputs in:

```text
outputs/
```

## Environment Setup

Create and activate a Python environment, then install dependencies:

```bash
pip install -r requirements.txt
```

Then start Jupyter:

```bash
jupyter notebook
```

Open:

```text
tcad_silicon_surrogate_tutorial.ipynb
```

## Expected Outputs

When the notebook is run successfully, it will create files such as:

```text
outputs/processed_curves_long_n.csv
outputs/processed_curve_matrix_n.csv
outputs/clustered_curve_metadata_n.csv
outputs/extracted_metrics_n.csv
outputs/surrogate_training_dataset_n.csv
outputs/trained_surrogate_n.pkl
outputs/pareto_front_ion_ioff_n.csv
outputs/pareto_ion_ioff_n.png
```

Cluster plots are saved under:

```text
outputs/cluster/
```

## Teaching Notes

The notebook is intentionally clean: code outputs and execution counts are cleared. Students should run the cells in order.

The current notebook focuses on nMOS data by default. The target MOS type can be changed in the setup cells if pMOS data are available and the same file conventions are followed.

## License

This teaching package is distributed under the MIT License. See `LICENSE` for details.
