# 🌬️ Wind Energy Assessment — Lone Star Wind Farm

> Assessing wind resource potential and estimating annual energy production for the Lone Star Wind Farm (Abilene, TX) using NREL data, Weibull distribution fitting, and turbine power curve modeling.

<p align="left">
  <img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white" alt="Python"/>
  <img src="https://img.shields.io/badge/Pandas-150458?style=flat-square&logo=pandas&logoColor=white" alt="Pandas"/>
  <img src="https://img.shields.io/badge/NumPy-013243?style=flat-square&logo=numpy&logoColor=white" alt="NumPy"/>
  <img src="https://img.shields.io/badge/Matplotlib-11557C?style=flat-square" alt="Matplotlib"/>
  <img src="https://img.shields.io/badge/Seaborn-444876?style=flat-square" alt="Seaborn"/>
  <img src="https://img.shields.io/badge/SciPy-8CAAE6?style=flat-square&logo=scipy&logoColor=white" alt="SciPy"/>
  <img src="https://img.shields.io/badge/Google%20Colab-F9AB00?style=flat-square&logo=googlecolab&logoColor=white" alt="Colab"/>
</p>

---

## Problem

Before investing in a wind farm, developers need a rigorous site assessment to determine whether the wind resource can support economically viable energy production. This project evaluates the Lone Star Wind Farm site in Abilene, TX by analyzing a full year of meteorological data to answer: How much energy can a GAMESA G87-2.0 MW turbine produce here, and how reliable is the wind resource?

## Data

- **Source**: NREL Wind Resource Database (WRDB)
- **Location**: Lone Star Wind Farm — 299 FM 604, Abilene, TX 79601
- **Time period**: January 1 – December 31, 2020
- **Resolution**: 5-minute and 60-minute intervals
- **Variables**: Wind speed, wind direction, air pressure, and air temperature — all at 100m hub height
- **Turbine**: GAMESA G87-2.0 MW (cut-in: 4 m/s, cut-out: 25 m/s)

## Approach

- Cleaned and validated the dataset, identifying outliers (0.18% wind speed, 1.50% air pressure)
- Analyzed wind direction patterns using wind rose plots — dominant flow from the South (180°)
- Fitted a **Weibull distribution** to the wind speed data to characterize resource consistency
- Mapped cleaned wind speeds to the manufacturer's power curve using interpolation to estimate theoretical power output
- Adjusted power output for real-world **air density variations** using pressure and temperature data
- Calculated capacity factor and scaled energy production to annual estimates
- Analyzed seasonal and hourly wind speed trends to identify peak generation periods

## Key Results

| Metric | Value |
|---|---|
| **Weibull Shape Parameter (k)** | 2.92 — indicates a consistent, low-variability wind resource |
| **Weibull Scale Parameter (c)** | 10.82 m/s — strong average wind speed |
| **Dominant Wind Direction** | South (180°), with secondary contribution from North |
| **Annual Energy Production (est.)** | 8,331 MWh |
| **7-Day Average Capacity Factor** | 64.95% |
| **Air Density Adjustment** | Improved energy yield accuracy by accounting for site-specific conditions |

## How to Run

```bash
# Clone the repo
git clone https://github.com/patilshan/wind-energy-assessment.git
cd wind-energy-assessment

# Install dependencies
pip install pandas numpy matplotlib seaborn scipy

# Launch the notebook
jupyter notebook Wind_Assessment.ipynb

# Or open directly in Google Colab via the badge in the notebook
```

## Project Structure

```
├── Wind_Assessment.ipynb    # Full analysis notebook
└── README.md
```

## What I Learned

- How to apply Weibull distribution fitting to characterize wind resources — a k value above 2 signals a bankable, consistent site
- The importance of adjusting theoretical power curves for local air density, which meaningfully changes energy yield estimates
- Wind rose analysis for turbine orientation decisions — the strong southern dominance at this site simplifies layout planning
- Working with high-resolution (5-minute interval) time-series data across an entire year

---

<p align="center">
  <a href="https://github.com/patilshan">← Back to profile</a>
</p>
