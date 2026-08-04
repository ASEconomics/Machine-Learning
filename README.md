# China Syndrome DML-IV Extension

## Paper

**Autor, D., Dorn, D., & Hanson, G. H. (2013).**
*The China Syndrome: Local Labor Market Effects of Import Competition in the United States.*
*American Economic Review*, **103**(6), 2121–2168.

---

## Authors

* Alexander Schwarze
* Fraser Small

**Course:** EC610I – Machine Learning in Economics
**Institution:** Wilfrid Laurier University

---

## Replication Objective

This repository reproduces **Table 3** from Autor, Dorn, and Hanson (2013) using Python.

The repository also extends the original analysis using **Double Machine Learning Instrumental Variables (DML-IV)**. The extension estimates the same six specifications using the DoubleML framework with the following machine learning learners:

* Ridge Regression
* Lasso Regression
* Random Forest
* Gradient Boosting
* Neural Network

The objective is to compare the original instrumental variable estimates with modern machine learning approaches while preserving the original identification strategy.

---

## Python Requirements

The notebook was developed using **Python 3.11**.

Required packages:

```text
numpy
pandas
scipy
matplotlib
geopandas
scikit-learn
linearmodels
doubleml
```

Install the required packages using

```bash
pip install numpy pandas scipy matplotlib geopandas scikit-learn linearmodels doubleml
```

---

## Repository Structure

```text
Machine-Learning/

│
├── China Syndrome DML-IV ExtensionV2.ipynb
├── AI_DISCLOSURE.md
│
├── Public-Release-Data/
│   └── dta/
│       └── workfile_china.dta
│
├── shapefiles/
│   ├── cz1990.shp
│
└── output/
```

---

## Data

All data required to reproduce the analysis are included in this repository.

The required files are

```text
Public-Release-Data/dta/workfile_china.dta

shapefiles/
    cz1990.shp
```

No additional downloads are required.

---

## Running the Code

Run the notebook

```text
China Syndrome DML-IV ExtensionV2.ipynb
```

from the first cell to the last.

The notebook performs the following tasks:

1. Imports the required Python packages.
2. Loads the ADH replication dataset.
3. Defines the six Table 3 specifications.
4. Estimates the original IV regressions.
5. Estimates the Double Machine Learning IV regressions.
6. Produces a comparison table of all estimators.
7. Generates coefficient comparison plots.
8. Generates coefficient path plots.
9. Produces three commuting zone maps.

---

## Running Order

Only a single notebook is required.

Execute every cell sequentially from top to bottom.

---

## Expected Outputs

The notebook creates an `output` folder containing:

### Tables

* `dml_results.tex`

### Figures

* `dml_coefficient_plot.png`
* `dml_coefficient_plot.pdf`
* `dml_coefficient_paths.png`
* `dml_coefficient_paths.pdf`
* `cz_import_penetration.png`
* `cz_import_penetration_continuous.png`
* `cz_nn_effect.png`

Additional PDF and SVG versions are generated where applicable.

---

## Known Replication Limitations

* The original IV estimates reproduce the specification of Autor, Dorn, and Hanson (2013) using Python rather than Stata.
* The Double Machine Learning extension preserves the original empirical specification but replaces the nuisance models with flexible machine learning estimators.
* The original IV regressions use state-clustered standard errors. The DML estimates currently use the default inference provided by the `DoubleMLPLIV` estimator.
* Small numerical differences may occur across software versions because of differences in optimization routines and machine learning implementations.

---

## Acknowledgements

This project was completed by **Alexander Schwarze** and **Fraser Small** for **EC610I – Machine Learning in Economics** at **Wilfrid Laurier University**.

The project builds upon the publicly available replication materials provided by Autor, Dorn, and Hanson (2013).
