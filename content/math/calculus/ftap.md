---
title: Fundamental theorem of asset pricing
date: 2025-08-28
type: book
math: true
weight: 15
---
In financial engineering, the most basic goal is to determine the price of a derivative.  
To achieve this, we need to establish a universal law of pricing, which is called the **Fundamental Theorem of Asset Pricing**.  
There are two such theorems. In this section, I will present these theorems and explain how we can use them to price derivatives.

# Fundamental Theorem of Asset Pricing I

This theorem states that if the market has no arbitrage opportunities, then there exists at least one equivalent martingale measure(EMM). In financial markets, if arbitrage opportunities exist, participants will quickly exploit them.Therefore, we can assume that markets are free of arbitrage. This theorem implies that we can always find an EMM to price any derivative. An **Equivalent Martingale Measure (EMM)** is a probability measure under which the **discounted price process of assets becomes a martingale**. 

To prove 

Assume there are two assets in the market:  

1. A **risk-free bond** with value  
   \[
   B_0 = 1, \quad B_T = (1+r).
   \]  

2. A **stock** with current price \(S_0\). At time \(T\), the stock can take two possible values:  
   \[
   S_T = uS_0 \quad \text{(up state)}, \qquad S_T = dS_0 \quad \text{(down state)},
   \]  
   where \(u > d > 0\).  
