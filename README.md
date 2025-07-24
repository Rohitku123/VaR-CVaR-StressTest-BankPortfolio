# VaR-CVaR-StressTest-BankPortfolio
Value at Risk (VaR), Conditional Value at Risk (CVaR), and Stress Testing using monte Carlo and parametric methods on a portfolio of four international banks:
This project evaluates the risk of a portfolio comprising four major global banks—Bank of America (BAC), Citigroup (C), UBS Group (UBS), and Deutsche Bank (DB)—using statistical risk measures like Value at Risk (VaR), Conditional Value at Risk (CVaR), and Stress Testing.


 Objective
To assess the downside risk and stress performance of a multi-asset bank portfolio using:

Historical price data from Yahoo Finance

Parametric approach for VaR and CVaR

10-day forward risk estimation

Scenario-based Stress Testing

🛠 Tools & Libraries
Python

Pandas, NumPy

yFinance

Matplotlib, Seaborn

Scipy Stats

 Assumptions
Portfolio value: $1,000,000

Weights assigned:

BAC: 30%

C: 30%

UBS: 20%

DB: 20%

Confidence levels: 90%, 95%, 99%

Parametric approach assumes returns are normally distributed

Historical data from July 2020 to July 2025

 Methodology
Download and Clean Price Data

Extracted close prices of 4 banks

Computed daily returns and handled NaNs

Portfolio Return & Volatility Calculation

Weighted mean of returns

Portfolio standard deviation using covariance matrix

Value at Risk (VaR)

Parametric approach using z-scores at 90%, 95%, 99% confidence

Also extended to a 10-day horizon

Conditional VaR (CVaR)

Expected shortfall beyond the VaR threshold

Calculated using the formula:

CVaR
𝛼
=
𝜙
(
𝑧
𝛼
)
1
−
𝛼
⋅
𝜎
⋅
𝑉
CVaR 
α
​
 = 
1−α
ϕ(z 
α
​
 )
​
 ⋅σ⋅V
Stress Testing / Scenario Analysis

Simulated extreme losses using Monte Carlo with shocks

Analyzed performance under adverse return conditions

 Results Summary
Metric	1-Day VaR	10-Day VaR	1-Day CVaR	10-Day CVaR
99%	$84,656	$267,675	$108,174	$341,948
95%	$61,875	$195,625	$77,931	$246,334
90%	$52,485	$165,931	$63,754	$201,393

Risk increases non-linearly with time due to volatility scaling.

CVaR > VaR always, indicating the average loss in worst-case scenarios is much worse than the threshold cut-off.

Stress testing showed potential extreme losses as high as ~$140,000–$150,000, emphasizing need for capital buffers.

 Interpretation
The portfolio shows moderate risk at the 95% confidence level with daily VaR of ~$61k.

A 10-day holding period significantly increases risk, almost tripling losses.

Stress testing reveals that under extreme market conditions, losses may exceed VaR estimates, justifying the use of CVaR for better risk insight.

 Conclusion
This project demonstrates a full-stack risk analysis pipeline with VaR, CVaR, and stress testing applied on a realistic financial portfolio. The techniques used are aligned with practices in quantitative finance, risk management, and regulatory stress testing frameworks such as CCAR.

