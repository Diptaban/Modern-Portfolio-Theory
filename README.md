# Quantitative Portfolio Optimization using Modern Portfolio Theory (MPT)



## Project Overview
This dissertation project explores the application of the **Markowitz Mean-Variance Framework** (Modern Portfolio Theory) within the high-volatility environment of the Indian banking sector. By moving beyond traditional monthly snapshots, this study interrogates daily market "noise" to find the mathematical "sweet spot" known as the **Efficient Frontier**.

The primary objective is to solve the investor's dilemma of uncertainty by balancing **systematic risk** (market-wide danger) and **unsystematic risk** (asset-specific danger) through data-driven diversification.



---

## Technical Workflow
The project is implemented in Python and follows a rigorous five-phase methodology:

### 1. Data Extraction & Normalization
* **Data Source:** Historical daily closing prices for Axis Bank, HDFC Bank, ICICI Bank, and SBI are retrieved via the `yfinance` library.
* **Transformation:** Raw price fluctuations are converted into **logarithmic returns** to ensure time-additivity and statistical stationarity, which are essential for rigorous modeling.

### 2. Parameter Modeling
* **Financial Engine:** Python functions calculate the **Mean Returns** (annualized by a factor of 252) and the **Portfolio Risk** (Standard Deviation).
* **Covariance Matrix:** The model utilizes a covariance matrix to capture the interdependence and diversification benefits between the selected banking stocks.



### 3. Monte Carlo Simulation
* **Stochastic Sampling:** Rather than solving a single equation, the algorithm executes a **Monte Carlo Simulation** with **100,000 iterations**.
* **Random Weighting:** For each iteration, a `weightscreator` function generates random asset allocations that sum exactly to 1.0 (100%), mapping out a "cloud" of possible risk-return scenarios.



### 4. Efficient Frontier Mapping
* **Visualization:** Using `Matplotlib`, the simulated portfolios are plotted on a scatter plot.
* **Optimization Points:** The algorithm identifies the **Minimum Variance Portfolio (MVP)** for risk-averse investors and the **Maximum Return Portfolio** for growth-oriented investors.

### 5. Optimal Weight Extraction
* **Final Selection:** A secondary high-iteration loop (up to 1,000,000 runs) is performed to pinpoint the exact asset weights required to reach the efficient edge.
* **Benchmark Performance:** The project compares the optimized results against the **Nifty 50 Index** to validate the model's "Alpha" and risk-adjusted superiority.

---

## Key Findings
* **The "Efficient" Edge:** The model identifies a Maximum Return Portfolio yielding approximately **30.49% annualized return** at a **24.21% risk factor** for the studied window.
* **Asset Dominance:** For the January 2024 to February 2026 dataset, the algorithm significantly favored **State Bank of India (SBI)**, allocating it roughly **97.6%** of the weight to maximize growth.
* **Diversification Paradox:** Due to the high correlation (often >0.7) between Indian bank stocks, the project highlights a "diversification ceiling" inherent in single-sector portfolios.




