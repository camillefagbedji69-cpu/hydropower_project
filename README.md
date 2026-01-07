# 🌊 Probabilistic Hydropower Assessment – Tanougou Falls

## 📌 Project Overview

This project provides a stochastic evaluation of the hydroelectric potential of the **Tanougou Falls** (Atacora, Benin). Instead of a traditional deterministic estimate, this model uses **Monte Carlo simulations** to account for hydrological variabaility and the mechanical aging of infrastructure over a 50-year horizon.

The goal is to determine the **P90 (Exceedance Probability)**, a critical financial and technical benchmark for renewable energy projects.

## 🎯 Key Objectives

* **Uncertainty Quantification:** Modeling inter-annual discharge variability using a Log-normal distribution ($\sigma = 0.4$).
* **Aging Simulation:** Incorporating an exponential decay of turbine efficiency (\eta$) over time.
* **Risk Benchmarking:** Extracting P50 (median) and P90 (safe threshold) indicators for energy planning.

## 🧠 Model Physics & Stochasticity

The instantaneous power is governed by the classic hydraulic equation:
                                 $$P(t) = \rho \cdot g \cdot H \cdot Q(t) \cdot \eta(t)$$


### Stochastic Variables:
1. **Hydrology ($Q$):** Modeled as a **Log-normal process** to reflect the reality of tropical river regimes where extreme low-flows and peak floods are non-symmetrical.
2. **Efficiency ($\eta$):** Modeled with a random degradation rate $\delta \in [0.005, 0.015]$, representing a loss of 0.5% to 1.5% efficiency per year due to wear and siltation.

## 📊 Key Findings & Results

After **1,000 simulations** over a 50-year lifecycle, the model yields the following insights:

| Metric | Value (Annual) | Interpretation |
| --- | --- | --- |
| **P50 (Median)** | **1.33 GWh** | The "Expected" production in a normal year. |
| **P90 (Safe Yield)** | **1.18 GWh** | The guaranteed threshold for **90% of scenarios**. |
| **Risk Margin** | **~11%** | The gap between P50 and P90, indicating high project stability. |

### Decisional Insight:

The **P90 value of 1.18 GWh/year** demonstrates that the site can reliably power approximately **9 200 households** even under severe hydrological stress. The narrow gap between the median and the P90 suggests that Tanougou is a low-risk, high-reliability site for decentralized electrification.


## 🛠️ Implementation

* **Language:** Python 3.13
* **Libraries:** `numpy` (stochastic engine), `pandas` (data synthesis), `matplotlib` (visualization).
* **Framework:** Monte Carlo sampling with 1,000 iterations.


## 🔮 Future Extensions

* **Climate Change Stress Test:** Increasing  to simulate higher rainfall volatility.
* **Financial Layer:** Integrating Levelized Cost of Energy (LCOE) and Net Present Value (NPV) based on P90 production.
* **Nexus LULC-Hydro:** Linking upstream deforestation to increased runoff variance in the Monte Carlo engine.
