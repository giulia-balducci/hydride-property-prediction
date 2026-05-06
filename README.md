# Hydride Property Screening

Predicting desorption temperature and effective hydrogen release in metal hydride systems using structural and compositional features, with the goal of screening candidate materials for near-room-temperature solid-state hydrogen storage.

---

## Motivation

Solid-state hydrogen storage in metal hydrides is a promising route to safe, high-density energy storage. However, most known hydrides either release hydrogen at temperatures too high for practical use, or fail to release their full theoretical capacity under real conditions. Nanostructuring can shift both parameters significantly.

This project applies machine learning to predict two key properties:
- **Desorption temperature** (target: near room temperature)
- **Effective hydrogen release** (actual wt% H₂ released vs. theoretical maximum)

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
│   └── 04_modelling.ipynb
├── src/                       # Reusable functions and utilities
├── results/                   # Model outputs, figures, evaluation metrics
├── requirements.txt
└── .gitignore
```

---

## Data Sources

- [Materials Project](https://materialsproject.org/): structural and compositional features
- [NIST Hydrogen Storage Materials Database](https://materials.nist.gov/materials/h2/): experimental reference data
- [HYDPARK](http://hydpark.ca.sandia.gov/): experimental thermodynamic data for hydrides
- Peer-reviewed literature (manual curation where needed)

---

## Methods

- Feature engineering from composition and crystal structure
- Regression models for desorption temperature and hydrogen release efficiency
- Particle size / nanostructuring as an explicit feature
- SHAP for model interpretability

*Modelling approach to be updated as the project develops.*

---

## Domain Context

This project is directly informed by my doctoral research on lightweight metal hydride–hydroxide systems for solid-state hydrogen storage (University of Glasgow, WestCHEM, 2011–2015), including experimental work on LiOH–MgH₂ and related nanostructured systems, and neutron diffraction experiments at ISIS Rutherford Appleton Laboratory.

---

## Status

🔬 In progress: data collection phase

---

## Author

**Giulia Balducci**
PhD Materials Chemistry | Data Scientist
[LinkedIn](https://www.linkedin.com/in/giuliabalducci) · [GitHub](https://github.com/giulia-balducci)
