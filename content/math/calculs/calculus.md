---
title: Browain motion
date: 2025-08-24
type: book 
math: true
---

In financial engineering (FE), one of the most fundamental tasks is option pricing. Among the various types of options, the European option plays a central role, as it admits a closed-form solution. Therefore, to build a comprehensive understanding of FE, the first step is to study the European option. This chapter introduces the essential mathematical tools needed to analyze and price such instruments.

# What is a Derivatives?
A derivative is a financial contract between two counterparties whose value depends on the performance of an underlying asset. When entering into an option contract, the parties agree on several key terms: the maturity date, the underlying asset, and the strike price. A European option is a type of derivative whose payoff depends solely on the price of the underlying asset at the maturity date.

In an option contract, the buyer has the right, but not the obligation, to exercise the option if it is favorable. Because of this right, the option buyer must pay a premium (the option price) at the initial time. The seller, in turn, accepts the obligation to fulfill the contract if the buyer decides to exercise.

The central task of option pricing theory is to determine the fair option price—that is, the price at which both counterparties are willing to enter into the agreement. This price ensures that neither party has an arbitrage opportunity and that the risk is fairly compensated.

# Elements of pricing a option.

To price an option, we need a model for its underlying asset, which is most commonly a stock.
The Black–Scholes model assumes that the dynamics of the stock price follow the stochastic differential equation (SDE):

$$ dS_t = \mu S_t dt + \sigma S_t dB_t $$
where $S_t$ is the stock price at time $t$, $\mu$ is the drift term, $\sigma$ is the volatility (diffusion term), and $B_t$ denotes a standard Brownian motion.

To fully understand this equation, one must first understand the concept of Brownian motion.
Brownian motion is a stochastic process with normally distributed increments, continuous paths, and independent stationary increments. It serves as the mathematical foundation for modeling random fluctuations in financial markets.

Here is a test.