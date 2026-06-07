# DDPG Crypto Trading Model
UCL MSc Financial Technology · Advanced Machine Learning · 2025

Reinforcement learning model (Deep Deterministic Policy Gradient) for BTC/USD trading under realistic fee constraints. Built and evaluated across three fee regimes: no fees, flat rate (0.1%), and tiered taker fees modelled on major crypto exchanges.

## Key findings

- Achieved 8.3% ROI and Sharpe ratio ~1.5 in a frictionless (no-fee) environment
- High-frequency RL strategies are fundamentally uneconomical under realistic fee structures - fee drag erodes returns even when the underlying strategy is profitable without costs
- The tiered fee model yielded 1.42% ROI vs -5.73% under a flat fee, as the agent rapidly traded its way into lower fee tiers
- Buy-and-hold remained a tough benchmark at 8.31% ROI with minimal transaction costs

## Methodology

- DDPG actor-critic architecture with sequential experience replay buffer to preserve temporal dependencies in financial time series
- State space: BTC/USD close price, volume, trend strength (MACD + SMA), volatility, ATR, log returns, RSI zone
- Continuous action space \[-1, 1] allowing fractional position sizing
- Decaying Gaussian exploration noise during training
- Benchmarked against buy-and-hold baseline across all three fee regimes

# [Paper](https://github.com/sharris-research/ddpg-crypto-trading/blob/main/ddpg-crypto-trading.pdf)

Individual coursework. Academic work only - not financial advice.
