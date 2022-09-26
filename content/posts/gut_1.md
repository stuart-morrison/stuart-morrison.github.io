---
title: "Some problems in probability theory"
summary: Some fun problems from Gut
date: 2022-09-25
draft: false
# weight: 1
# aliases: ["/first"]
tags: ["random variables", "probability"]
author: "sjm"
showToc: false
TocOpen: false
hidemeta: false
comments: false
disableHLJS: true # to disable highlightjs
disableShare: false
disableHLJS: false
hideSummary: true
searchHidden: false
ShowReadingTime: false
ShowBreadCrumbs: false
ShowPostNavLinks: false
ShowRssButtonInSectionTermList: false
ShowShareButtons: false
mathjax: true

---

## Find the distribution of a cumulative distribution function

Take a cumulative distribution function $F$ of random variable $X$. Let $Z = F_{X}(x)$. Then:
$F_{Z}(x) = P(Z < x) = P(F_{X}(x) < x) = P(X < F^{-1}_{X}(x)) = F_X (F^{-1}_X (x)) = x$

So then $Z$, the cumulative distribution function of $X$, is uniformly distributed.

## Three problems from Gut

From Gut, Probability: A Graduate Course, Chapter 2.

**Question 5: Show $\sum P(n < X \neq n + m) = m$**

For a discrete valued random variable $X \in \mathbb{Z}$:
$$\sum_{\mathbb{Z}} P (n < X \leq n + m) = \sum_{i \in \mathbb{Z}}\sum_{n = i+1}^{i+m} P(X = n)$$
$$=m\cdot \sum_{i \in \mathbb{Z}} P(X = i) = m \cdot 1 = m$$

**Question 6: Show $\int P(x < X \leq x + a) = a$**

For a continuously valued random variable over $(-\infty, \infty)$:
$$\int_{-\infty}^{\infty} P(x < X \leq x + a) dx = \int_{-\infty}^{\infty} \int_{u = x}^{x+a}f(u) du dx$$
$$ = \int_{u = x-a}^{x} \int_{-\infty}^{\infty} f(x) dx du = \int_{u = x-a}^{x} (F(\infty) - F(-\infty)) du$$
$$=\int_{u = x-a}^{x} 1 du = x - x+a = a$$

**Question 15: Find $\int P(X < x \leq Y) - P(Y < x \leq X)$**

For two continuously-valued random variables, $X$, $Y$, find $\int_{-\infty}^{\infty} P(X < x \leq Y) - P(Y < x \leq X) dx$

$$\int_{-\infty}^{\infty} P(X < x \leq Y) - P(Y < x \leq X) dx = \int_{-\infty}^{\infty} \left[\int_{x}^{\infty}f_{Y} (u) du \int_{-\infty}^{x} f_{X}(u) du  - \int_{-\infty}^{x}f_{Y} (u)du  \int_{x}^{\infty} f_{X}(u) du  \right]dx$$
$$= \int_{-\infty}^{\infty} \left[\left(1 - F_{Y}(x) \right)\left(F_{X}(x) - 0\right) - \left(F_{Y}(x) - 0 \right)\left(1 - F_{X}(x)\right) \right]dx$$
$$= \int_{-\infty}^{\infty} \left[\left(F_{X}(x) - F_{X}(x)F_{Y}(x)\right) - \left(F_{Y}(x) - F_{X}(x)F_{Y}(x)\right) \right]dx =  \int_{-\infty}^{\infty} F_{X}(x) - F_{Y}(x) dx$$
$$=\left[ xF_{X} (x) \rvert_{-\infty}^{\infty} - \int_{-\infty}^{\infty}xf_{X} (x) dx \right] - \left[ xF_{Y} (x) \rvert_{-\infty}^{\infty} - \int_{-\infty}^{\infty}xf_{Y} (x) dx \right]$$
$$= E[Y] - E[X]$$

Phew!