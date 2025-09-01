---
title: Basic Calculus
date: 2025-08-24
type: book 
math: true
weight: 10
---

This section uses Brownian motion as a worked example to illustrate how calculus can be applied to derive the Black–Scholes formula mathematically. The financial meaning will cover in another part.
# Rules of Calculus.
Since Brownian motion has independent increments, we know that  

$$
B_t \sim \mathcal{N}(0, t).
$$  

Thus, its cumulative distribution function (CDF) is  

$$
F(x) = \int_{-\infty}^x \frac{1}{\sqrt{2\pi t}} 
       e^\left(-\frac{y^2}{2t}\right) dy.
$$  

By definition, the probability density function (PDF) is the derivative of the CDF:  

$$
f(x) = \frac{d}{dx} F(x) 
     = \frac{d}{dx}\int_{-\infty}^x \frac{1}{\sqrt{2\pi t}} 
       e^\left(-\frac{y^2}{2t}\right) dy.
$$  

Intuitively, one may think of the differentiation operator $\frac{d}{dx}$ and 
the integration sign $\int$ as **inverse operations** when they are applied closely together.  
Although this is not fully rigorous, it reflects the **Fundamental Theorem of Calculus**, 
which justifies exchanging the derivative and the integral in this case.  

Therefore, the PDF of Brownian motion at time $t$ is  

$$
f(x) = \frac{1}{\sqrt{2\pi t}} 
       e^\left(-\frac{x^2}{2t}\right).
$$
## Expectation of Brownian Motion

We want to compute the mean of Brownian motion at time $t$:  

$$
\mathbb{E}[B_t] = \int_{-\infty}^{\infty} x \cdot 
\frac{1}{\sqrt{2\pi t}} e^\left(-\frac{x^2}{2t}\right) dx.
$$

This integral looks complicated, but notice that the integrand 
involves $x e^{-x^2/(2t)}$, which is (up to a constant factor) 
the derivative of a Gaussian exponential.  

Indeed,
$$
\frac{d}{dx} \left( e^{-\frac{x^2}{2t}} \right) 
= -\frac{x}{t} e^{-\frac{x^2}{2t}}.
$$

Therefore,
$$
x e^{-\frac{x^2}{2t}} = -t \frac{d}{dx}\left(e^{-\frac{x^2}{2t}}\right).
$$

Plugging this into the expectation integral, we get

$$
\mathbb{E}[B_t] 
= \int_{-\infty}^{\infty} x \cdot 
\frac{1}{\sqrt{2\pi t}} e^{-\frac{x^2}{2t}} dx
= -\frac{t}{\sqrt{2\pi t}} 
\int_{-\infty}^{\infty} \frac{d}{dx}\left(e^{-\frac{x^2}{2t}}\right) dx.
$$
Now, applying the Fundamental Theorem of Calculus,
$$
\int_{-\infty}^{\infty} \frac{d}{dx}\left(e^{-\frac{x^2}{2t}}\right) dx
= \left. e^{-\frac{x^2}{2t}} \right|_{-\infty}^{\infty} = 0 - 0 = 0.
$$
Hence,
$$
\mathbb{E}[B_t] = 0.
$$

## Variance of Brownian Motion

The variance of Brownian motion at time $t$ is defined as

$$
\mathrm{Var}(B_t) = \mathbb{E}[B_t^2] - \big(\mathbb{E}[B_t]\big)^2.
$$

Since we have already shown that $\mathbb{E}[B_t] = 0$, this reduces to

$$
\mathrm{Var}(B_t) = \mathbb{E}[B_t^2].
$$

By definition of expectation under the density of $B_t \sim \mathcal{N}(0,t)$,  

$$
\mathbb{E}[B_t^2] = \int_{-\infty}^{\infty} 
x^2 \cdot \frac{1}{\sqrt{2\pi t}} 
e^`\left(-\frac{x^2}{2t}\right) dx.
$$

---

### Step 1: Integration by Parts Setup
Recall the **integration by parts formula** (from the product rule):

$$
\int f(x)\, g'(x)\, dx = f(x)g(x) - \int f'(x)\, g(x)\, dx.
$$

We choose:
- $f(x) = x$, so $f'(x) = 1$,
- $g'(x) = x \cdot \frac{1}{\sqrt{2\pi t}} e^{-\frac{x^2}{2t}}$,  
  so that the integrand $x^2 \cdot \frac{1}{\sqrt{2\pi t}} e^{-\frac{x^2}{2t}}$ is represented.

---

### Step 2: Derivative Identity
Notice that

$$
\frac{d}{dx}\left( e^{-\frac{x^2}{2t}} \right) = -\frac{x}{t} e^{-\frac{x^2}{2t}}.
$$

This identity will help simplify the calculation.

---
Use substitution rules, $\sqrt{t}y = x$, we have    
### Step 3: Known Result
Alternatively, we can recognize that $B_t \sim \mathcal{N}(0,t)$ is a normal random variable.  
For a normal distribution $\mathcal{N}(0, \sigma^2)$, we know

$$
\mathbb{E}[X^2] = \sigma^2.
$$

Thus directly,

$$
\mathbb{E}[B_t^2] = t.
$$

---

### Final Result
Therefore, the variance of Brownian motion is

$$
\mathrm{Var}(B_t) = t.
$$

