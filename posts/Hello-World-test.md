---
date: '2025-07-28'
title: Check if a Number is Divisible by Exactly One of the Given Numbers
description: "Write a function\_div_by_exactly_one\_that takes three integers\_num,\_a, and\_b. The function should return\_True\_if\_num\_is divisible by exactly one of the numbers\_a\_or\_b, and\_False\_otherwise."
imageSrc: >-
  https://raw.githubusercontent.com/simplearyan/stick-hero/main/assets/Screenshot.png
image: >-
  https://images.unsplash.com/photo-1747895684398-be9211eebf24?q=80&w=1170&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D
category: Python
slug: check-if-a-number-is-divisible-by-exactly-one-of-the-given-numbers
tags:
  - Python
  - IIT
---


<img src="https://r2cdn.perplexity.ai/pplx-full-logo-primary-dark%402x.png" class="logo" width="120"/>

## Check if a Number is Divisible by Exactly One of the Given Numbers

Write a function div_by_exactly_one that takes three integers num, a, and b. The function should return True if num is divisible by exactly one of the numbers a or b, and False otherwise.
NOTE: This is a function type question, you don't have to take input or print the output, just have to complete the required function definition.

Here's the function definition as required:

```python
def div_by_exactly_one(num, a, b):
    # Check divisibility by a and b
    is_div_by_a = (num % a == 0)
    is_div_by_b = (num % b == 0)
    # Return True if exactly one is True (XOR)
    return is_div_by_a ^ is_div_by_b
```

**Explanation:**

- `is_div_by_a` is `True` if `num` is divisible by `a`.
- `is_div_by_b` is `True` if `num` is divisible by `b`.
- The `^` operator is logical XOR; it returns `True` if and only if one (and only one) of the operands is `True`.
- This meets the requirement: "exactly one of the numbers a or b".

