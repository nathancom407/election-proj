
# Election Projection ML Model and Causal Inference Exploration

This repository contains a data-driven analysis of the 2022 U.S. House and Senate elections. The goal is to investigate and model the relationship between campaign finance and electoral success using machine learning and causal inference techniques.

## Project Objectives

This project seeks to answer two primary research questions:

### **RQ1:**  
**Can we predict a candidate’s share of the vote (%) using campaign finance data?**  
We use regression-based machine learning models (OLS, KNN, Random Forest) and various feature transformations (e.g., log-scaling, encoding) to model vote percentage.

### **RQ2:**  
**Does campaign spending cause changes in election outcomes?**  
We treat campaign spending as a binary treatment (top spender or not) and evaluate its causal impact on vote share using statistical inference and adjustment for confounding variables.

## Datasets Used

- **Candidate Summary 2022** from the FEC: Contains disbursement, contribution, and party data.
- **US Senate and House Results 2022**: Includes vote percentages and election outcomes.

All datasets are cleaned and merged to align candidate spending with actual election results by race and FEC ID.

## Exploratory Data Analysis (EDA)

The `EDA.ipynb` notebook includes:
- Parsing and cleaning candidate and election datasets
- Visualization of vote share distributions
- Winner breakdowns by state and party
- Preprocessing steps like converting percentages, combining House/Senate data

## Methodology

### RQ1 (Prediction Modeling)
- Used models: **OLS (GLM)**, **KNN**, **Random Forest**
- Key features: total contributions, disbursements, party affiliation
- Preprocessing: log-transformations, one-hot encoding, removal of collinear variables
- Best performance: **KNN improved substantially after feature scaling**, with higher R² and lower RMSE.

### RQ2 (Causal Inference)
- Treatment: Candidate is top spender in race (binary)
- Outcome: Vote percentage
- Confounders: Incumbency, party, candidate status (open seat), state, gender, and office type
- Analysis: Compared top spenders to non-top spenders within the same race to estimate causal impact

## Technologies & Libraries

- Python (Pandas, NumPy, Scikit-learn, Statsmodels)
- Matplotlib / Seaborn for visualization
- Jupyter Notebooks for interactive analysis

## Repository Structure

```
Election Projection ML Model/
│
├── RQ1.ipynb                      # Vote % prediction using ML models
├── RQ2.ipynb                      # Causal inference: spending vs. vote share
├── EDA.ipynb                      # Data cleaning and exploratory visualizations
├── *.csv                          # Raw datasets (FEC and election results)
└── README.md                      # Project overview and documentation
```

## Future Directions

- Incorporate additional years of data for time-series comparisons
- Use matching or doubly robust estimation for improved causal inference
- Develop a dashboard to visualize electoral forecasts interactively

## Contact

Built by Nathan Comstock (https://github.com/nathancom407) in collaboration with David Li, Charlie Ginsburg, and Teoman Akca 

Email: nathanc.personal@gmail.com
