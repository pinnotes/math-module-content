---
date: 22-07-2025
title: Finding the Roots (Where the Graph Touches or Crosses the x-axis) 🌱
description: Write a function div_by_exactly_one that takes three integers num, a, and b. The function should return True if num is divisible by exactly one of the numbers a or b, and False otherwise.
imageSrc: https://raw.githubusercontent.com/simplearyan/stick-hero/main/assets/Screenshot.png
---

<img src="https://r2cdn.perplexity.ai/pplx-full-logo-primary-dark%402x.png" class="logo" width="120"/>

## Step-by-Step Explanation of the Solution 🚀

Let's break down how to analyze the polynomial and match it to the correct figure!

### 1. **Finding the Roots (Where the Graph Touches or Crosses the x-axis) 🌱**

Given:

$$
p(x) = 0.3x^3(x^2 - 1)(x - 2)^2(x - 3)
$$

- **$x^3$:** Root at $x = 0$ with multiplicity 3 (triple root)
- **$(x^2 - 1)$:** Roots at $x = 1$ and $x = -1$ (each single root)
- **$(x - 2)^2$:** Root at $x = 2$ with multiplicity 2 (double root)
- **$(x - 3)$:** Root at $x = 3$ (single root)

**Summary Table:**


| Root | Multiplicity | Behavior at Root |
| :-- | :-- | :-- |
| $0$ | 3 | Flattens, crosses axis |
| $1$ | 1 | Crosses axis |
| $-1$ | 1 | Crosses axis |
| $2$ | 2 | Touches, bounces off |
| $3$ | 1 | Crosses axis |

### 2. **Degree and End Behavior 🎢**

- **Expand the degree:**
    - $x^3$ → degree 3
    - $(x^2 - 1)$ → degree 2
    - $(x - 2)^2$ → degree 2
    - $(x - 3)$ → degree 1
- **Total degree:** $3 + 2 + 2 + 1 = 8$ (but let's check carefully: $x^3$ × $x^2$ × $x^2$ × $x$ = $x^{3+2+2+1} = x^8$). However, the original solution says degree 9—let's clarify:

$$
(x^2 - 1) = x^2 - 1 \implies \text{degree 2}
$$

$$
(x - 2)^2 = x^2 - 4x + 4 \implies \text{degree 2}
$$

So, multiplying:

- $x^3$ (degree 3)
- $(x^2 - 1)$ (degree 2)
- $(x - 2)^2$ (degree 2)
- $(x - 3)$ (degree 1)

Total degree: $3 + 2 + 2 + 1 = 8$.

**End Behavior (since leading coefficient is positive, 0.3):**

- Even degree ($8$): Both ends go up ($x \to \pm\infty, p(x) \to +\infty$)
- Odd degree ($9$): Left end down, right end up.

*But since the polynomial is degree 8, both ends go up!*

### 3. **Behavior at Each Root 🌈**

- **Triple root ($x = 0$)**: The graph flattens and crosses the x-axis.
- **Double root ($x = 2$)**: The graph just touches the x-axis and turns around (bounces).
- **Single roots ($x = 1, -1, 3$)**: The graph crosses the x-axis sharply.


### 4. **Putting It All Together: Matching the Figure 🖼️**

- **Check for all roots at correct places.**
- **Check that at $x = 0$, the graph flattens as it passes through.**
- **At $x = 2$, the graph touches and bounces (does not cross).**
- **At $x = 1, -1, 3$, the graph crosses the axis.**
- **Both ends of the graph rise up (since degree is even and leading coefficient is positive).**

If a figure shows all these features, **that is the correct graph for $p(x)$!**

## 🎯 **Final Answer**

**Figure 1** represents the polynomial \$ p(x) \$!
It has all the correct roots, the right behavior at each root, and the correct end behavior.

