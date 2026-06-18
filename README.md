# Hydride Property Screening

Predicting desorption temperature and effective hydrogen release in metal hydride systems using structural and compositional features, with the goal of screening candidate materials for near-room-temperature solid-state hydrogen storage.

---

## Motivation

Solid-state hydrogen storage in metal hydrides is a promising route to safe, high-density energy storage. However, most known hydrides either release hydrogen at temperatures too high for practical use, or fail to release their full theoretical capacity under real conditions. Nanostructuring can shift both parameters significantly.

This project applies machine learning to predict two key properties:
- **Desorption temperature** (target: near room temperature)
- **Effective hydrogen release** (experimentally measured hydrogen storage capacity (wt%))

The goal is to identify candidate materials worth investigating experimentally, informed by patterns learned from existing data.

---

## Project Structure

```
hydride-property-prediction/
│
├── data/
│   ├── raw/                   # Source data, unmodified
│   └── processed/             # Cleaned and feature-engineered datasets
├── notebooks/
│   ├── 01_data_collection.ipynb
│   ├── 02_eda.ipynb
│   ├── 03_preprocessing.ipynb
│   ├── 04_modelling.ipynb
│   └── 05_candidate_screening.ipynb
├── src/                       # Reusable functions and utilities
├── results/                   # Model outputs, figures, evaluation metrics
├── requirements.txt
└── .gitignore
```

---

## Data Sources

- [ML-HydPARK](https://pubs.acs.org/doi/abs/10.1021/acs.jpclett.9b02971) (Witman et al., *J. Phys. Chem. Lett.* 2019): ML-ready experimental thermodynamic data for metal hydrides, derived from the HYDPARK database.
- **ElementalH_Ef**: experimental elemental hydride formation energies, used for compositional feature engineering (`Ef_weighted`). Preferred over the Materials Project DFT equivalent due to fewer missing values and methodological consistency with ML-HydPARK.

---

## Methods

- Feature engineering from composition, thermodynamics and crystal structure, including a composition-weighted elemental hydride formation energy feature (Ef_weighted)
- Two regression models: Random Forest for hydrogen storage capacity (Dataset A) and Linear Regression for desorption temperature (Dataset B)
- SHAP for model interpretability

---

## Domain Context

This project is directly informed by my doctoral research on lightweight metal hydride–hydroxide systems for solid-state hydrogen storage (University of Glasgow, WestCHEM, 2011–2015), including experimental work on LiOH–MgH₂ and related nanostructured systems, and neutron diffraction experiments at ISIS Rutherford Appleton Laboratory.

---

## Status

✅ Complete. See Future Work in notebook 05 for planned extensions.
- Data collection: completed.
- EDA: completed.
- Feature selection and preprocessing: completed.
- Modelling – Dataset A (`Hydrogen_Weight_Percent`): completed. Random Forest (+ compositional Ef_weighted feature) achieves R²=0.765 on the test set. SHAP analysis completed.
- Modelling – Dataset B (`Temperature_oC`): completed. Linear Regression achieves validation R²=0.886 but generalises poorly (test R²=0.700, RMSE=87°C); the gap is consistent with overfitting on a small validation set and reflects insufficient training data (266 samples). Further modelling requires a larger dataset.
- Candidate screening: completed. Test set screening identifies 2 compounds above 3.5 wt%. Exploratory full-dataset screening identifies 18 candidates above 3.5 wt%, of which 2 exceed the DOE target of 5.0 wt% (Mg0.9Sc0.1 and La0.1Mg0.85Al0.05, both 6.2% actual).

---

## Author

**Giulia Balducci**
PhD Materials Chemistry | Data Scientist
[LinkedIn](https://www.linkedin.com/in/giuliabalducci) · [GitHub](https://github.com/giulia-balducci)
