# KMV

The KMV model is a structural credit risk model used to estimate the probability of a firm's default on its debt obligations. The model is based on the Merton model, which views a firm's equity as a call option on its assets, with the strike price being the value of the firm's debt.


Firm's Assets (V): The total market value of the firm's assets is denoted by V.

Firm's Debt (D): The total value of the firm's debt (liabilities) is denoted by D. The model typically uses the short-term liabilities plus half of the long-term liabilities as the default point.

Equity (E): The market value of the firm's equity is viewed as a call option on the firm's assets with a strike price equal to the value of the debt (D).

Asset Volatility (sigma_V): The volatility of the firm's assets, sigma_V, represents the uncertainty in the value of the firm's assets over time.

Equity Volatility (sigma_E): The volatility of the firm's equity, sigma_E, is observable in the market and used to infer sigma_V.

Risk-Free Rate (r): The risk-free interest rate, typically taken as the yield on government bonds.

Time Horizon (T): The time horizon over which the default probability is calculated, usually 1 year.


Merton's Model: In the Merton framework, the equity of the firm is modeled as a call option on the firm's assets:
E = V * N(d1) - D * exp(-r * T) * N(d2)
Where:
E is the market value of equity.
V is the market value of assets.
D is the value of debt.
r is the risk-free rate.
T is the time to maturity (typically 1 year).
N(.) is the cumulative distribution function of the standard normal distribution.

d1 and d2 are given by:
d1 = [ ln(V / D) + (r + 0.5 * sigma_V^2) * T ] / (sigma_V * sqrt(T))
d2 = d1 - sigma_V * sqrt(T)

Distance to Default (DD): The Distance to Default is a measure of how far the firm's asset value is from the default point (the value of its debt):
DD = (ln(V / D) + (r - 0.5 * sigma_V^2) * T) / (sigma_V * sqrt(T))
This represents the number of standard deviations the firm's asset value is away from the default point.

Expected Default Frequency (EDF): The Expected Default Frequency is the probability that the firm will default within the given time horizon, derived from the Distance to Default:
EDF = N(-DD)
Where N(-DD) is the probability that the firm's assets will fall below the default point.


Estimate Asset Value and Volatility:
Use market data (equity value E and equity volatility sigma_E) to estimate the firm's asset value V and asset volatility sigma_V.
This involves solving a system of equations based on the Black-Scholes-Merton option pricing formula.

Calculate Distance to Default:
Use the estimated asset value V and asset volatility sigma_V to calculate the Distance to Default (DD).
Calculate Expected Default Frequency (EDF):

Convert the Distance to Default into a probability of default using the cumulative distribution function of the normal distribution.
