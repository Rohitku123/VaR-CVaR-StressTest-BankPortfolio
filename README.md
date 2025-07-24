# VaR-CVaR-StressTest-BankPortfolio
Value at Risk (VaR), Conditional Value at Risk (CVaR), and Stress Testing using monte Carlo and parametric methods on a portfolio of four international banks:
This project evaluates the risk of a portfolio comprising four major global banks—Bank of America (BAC), Citigroup (C), UBS Group (UBS), and Deutsche Bank (DB)—using statistical risk measures like Value at Risk (VaR), Conditional Value at Risk (CVaR), and Stress Testing.


#  Portfolio Risk Analysis: VaR, CVaR & Stress Testing on Global Banks

This project performs a comprehensive **risk analysis** of a portfolio of four major global banks—**Bank of America (BAC), Citigroup (C), UBS Group (UBS), and Deutsche Bank (DB)**. Using **Parametric VaR**, **CVaR**, and **Stress Testing**, it assesses potential losses under normal and adverse market conditions.

---

##  Objective

- Calculate 1-day and 10-day **Value at Risk (VaR)** using the parametric method.
- Compute **Conditional VaR (CVaR)** (Expected Shortfall).
- Perform **stress testing** under hypothetical adverse scenarios.
- Understand tail risks in a global bank portfolio.

---

##  Assumptions

| Parameter              | Value                     |
|------------------------|---------------------------|
| Initial Portfolio Value| $1,000,000                |
| Portfolio Weights      | BAC: 30%, C: 30%, UBS: 20%, DB: 20% |
| Confidence Levels      | 90%, 95%, 99%             |
| Historical Data Range  | July 2020 to July 2025    |
| Data Source            | Yahoo Finance (`yfinance`) |
| Distribution Assumption| Normal (for parametric method) |

---

##  Technologies Used

- Python
- NumPy, Pandas
- yFinance
- Matplotlib, Seaborn
- SciPy Stats

---

##  Methodology

### 1. Data Collection & Cleaning
- Downloaded historical **closing prices** of 4 bank stocks.
- Calculated **daily returns** using percentage change.
- Dropped missing values and aligned the data.

### 2. Portfolio Return & Volatility
- Calculated **mean returns** and **covariance matrix**.
- Used **dot product** for portfolio mean return.
- Computed **portfolio standard deviation** using matrix algebra.

### 3. Value at Risk (VaR)
Used the **parametric (Gaussian)** method:

\[
\text{VaR}_{\alpha} = z_{\alpha} \cdot \sigma_p \cdot \sqrt{t} \cdot V
\]

Where:
- \( z_{\alpha} \) is the z-score at confidence level α
- \( \sigma_p \) is portfolio standard deviation
- \( t \) is time horizon (1-day or 10-day)
- \( V \) is portfolio value

### 4. Conditional VaR (CVaR)
Computed as:

\[
\text{CVaR}_{\alpha} = \frac{\phi(z_\alpha)}{1 - \alpha} \cdot \sigma_p \cdot \sqrt{t} \cdot V
\]

Where \( \phi(z_\alpha) \) is the standard normal PDF.

### 5. Stress Testing (Scenario Analysis)
- Applied **Monte Carlo simulations** and **shock-based stress** scenarios.
- Simulated adverse returns and their impact on portfolio value.

---

##  Key Results

###  Value at Risk (VaR)

| Confidence Level | 1-Day VaR ($) | 10-Day VaR ($) |
|------------------|---------------|----------------|
| **90%**          | 52,485        | 165,931        |
| **95%**          | 61,875        | 195,625        |
| **99%**          | 84,656        | 267,675        |

###  Conditional VaR (CVaR)

| Confidence Level | 1-Day CVaR ($) | 10-Day CVaR ($) |
|------------------|----------------|-----------------|
| **90%**          | 63,754         | 201,393         |
| **95%**          | 77,931         | 246,334         |
| **99%**          | 108,174        | 341,948         |

###  Stress Test Loss (Worst Simulated Outcomes)
- **Simulated max loss** in extreme scenarios: **~$140,000 to $150,000**

---

##  Interpretation

- The **1-day 95% VaR** of ~$61,875 means there's a 5% chance of losing **more than $61,875** in one day.
- **CVaR** quantifies average loss **beyond** the VaR threshold and is always **greater than VaR**.
- Extending to a **10-day horizon** significantly **amplifies potential losses** due to volatility scaling.
- **Stress testing** shows that **real-world risks** (especially in crises) can **exceed VaR/CVaR estimates**, justifying robust capital buffers.

---

##  Conclusion

This notebook demonstrates practical implementation of:

- Parametric **VaR and CVaR**
- Multi-asset portfolio risk evaluation
- Scenario-based **stress testing**

These methods are **aligned with financial risk regulations** like **CCAR**, **Basel II/III**, and are widely used in **investment banks, hedge funds**, and **risk management teams**.

---

##  Project Structure


