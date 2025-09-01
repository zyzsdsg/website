---
title: Calculus
date: 2025-08-24
type: book 
math: true
weight: 5
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


# Brownian Motion

At time \(t = 0\), a standard Brownian motion satisfies:

$$
B_0 = 0
$$

---

## Increment Distribution

The increment of Brownian motion over a small interval \([t, t+dt]\) is defined as:

$$
dB_t = B_{t+dt} - B_t
$$

and it follows a **normal distribution** with mean \(0\) and variance \(dt\):

$$
dB_t \sim \mathcal{N}(0, dt)
$$

---

## Independent Increments

If two intervals do not overlap, say \((u,v)\) and \((m,n)\), then the increments are **independent random variables**:

$$
B_v - B_u, \quad B_n - B_m
$$

# Normal Distributon

The normal distribution is a fundamental distribution, and its equation is:

$$
\int^{\infty}_{-\infty}\frac{1}{\sqrt{2\pi \sigma}}e^{-\frac{(x-\mu)^2}{2\sigma^2}}dx = 1
$$
Where $\mu$ is the mean of the random variable $x$, $\sigma ^2$ is the variance of $x$.

For the Browain motion, if the time interval is 1, the mean is 0 and variance is 1, which reduces to standard normal distribution, and its equation is:
$$
\int_{-\infty}^{\infty} \frac{1}{\sqrt{2\pi}} e^{-\frac{x^2}{2}} dx = 1
$$

If the interval is $t$ not 1, the equation change to:
$$
\int_{-\infty}^{\infty} \frac{1}{\sqrt{2\pi t}} e^{-\frac{x^2}{2t}} dx = 1
$$

These are called cumulative distribution functions (CDFs).  
If we consider the probability of a random variable $X$ being less than a number $x$, and denote the CDF as $F$, then the expression $F(x)$ means the probability of the random variable being less than $x$.

$$
F(x) = P(X \leq x) = \int_{-\infty}^x \frac{1}{\sqrt{2\pi t}} \, e^{-\frac{x^2}{2t}}  dx
$$

The derivative of $F(x)$ is the probability density function (PDF).  

For the **standard normal distribution**:
$$
f(x) = \frac{1}{\sqrt{2\pi}} e^{-\frac{x^2}{2}}
$$

For the **Brownian motion $B_t$ at time $t$**, since $B_t \sim \mathcal{N}(0,t)$:
$$
f(B_t) = \frac{1}{\sqrt{2\pi t}} e^{(-\frac{B_t^2}{2t})}
$$
