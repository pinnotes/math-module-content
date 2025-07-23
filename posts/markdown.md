---
date: 22-07-2025
title: Python Dictionary Operations | Step-by-Step Solutions 🍏🍌🍒
description: Write a function div_by_exactly_one that takes three integers num, a, and b. The function should return True if num is divisible by exactly one of the numbers a or b, and False otherwise.
imageSrc: https://raw.githubusercontent.com/simplearyan/stick-hero/main/assets/Screenshot.png
---

<img src="https://r2cdn.perplexity.ai/pplx-full-logo-primary-dark%402x.png" class="logo" width="120"/>

# Python Dictionary Operations: Step-by-Step Solutions 🍏🍌🍒

Let's implement each required function with clear explanations and easy-to-understand steps! Practice examples are included so you can try them out and see how they work. 🚀

## 1. `total_price(fruit_prices: dict, purchases) -> float`

**Compute the total price for a list of fruit purchases. (No `sum` function allowed!)**

### Step-by-Step Solution 🧩

- Loop through each `(fruit, quantity)` in `purchases`.
- Multiply the price of the fruit by its quantity.
- Add each result to a running total.
- Return the total.

```python
def total_price(fruit_prices: dict, purchases) -> float:
    total = 0.0
    for fruit, quantity in purchases:
        total += fruit_prices[fruit] * quantity
    return total
```


#### Practice Example

```python
fruit_prices = {'apple': 5, 'banana': 2}
purchases = [('apple', 2), ('banana', 3)]
print(total_price(fruit_prices, purchases))  # Output: 5*2 + 2*3 = 10 + 6 = 16.0
```

**Output:** `16.0` ✅

## 2. `total_price_no_loops(fruit_prices: dict, purchases) -> float`

**Compute the total price without using loops.**

### Step-by-Step Solution 🧩

- Use a generator expression inside the `sum` function to avoid explicit loops.

```python
def total_price_no_loops(fruit_prices: dict, purchases) -> float:
    return sum(fruit_prices[fruit] * quantity for fruit, quantity in purchases)
```


#### Practice Example

```python
print(total_price_no_loops(fruit_prices, purchases))  # Output: 16.0
```

**Output:** `16.0` ✅

## 3. `find_cheapest_fruit(fruit_prices:dict) -> str`

**Find the cheapest fruit without using `min`.**

### Step-by-Step Solution 🧩

- Initialize `cheapest_fruit` as `None` and `cheapest_price` as infinity.
- Loop through each fruit and price.
- If the price is lower than `cheapest_price`, update both variables.
- Return the fruit with the lowest price.

```python
def find_cheapest_fruit(fruit_prices:dict) -> str:
    cheapest_fruit = None
    cheapest_price = float('inf')
    for fruit, price in fruit_prices.items():
        if price < cheapest_price:
            cheapest_price = price
            cheapest_fruit = fruit
    return cheapest_fruit
```


#### Practice Example

```python
print(find_cheapest_fruit({'apple': 5, 'banana': 2, 'cherry': 7}))  # Output: 'banana'
```

**Output:** `'banana'` 🍌

## 4. `find_cheapest_fruit_no_loops(fruit_prices:dict) -> str`

**Find the cheapest fruit using `min`, no loops.**

### Step-by-Step Solution 🧩

- Use `min` with the `key` parameter.

```python
def find_cheapest_fruit_no_loops(fruit_prices:dict) -> str:
    return min(fruit_prices, key=fruit_prices.get)
```


#### Practice Example

```python
print(find_cheapest_fruit_no_loops({'apple': 5, 'banana': 2, 'cherry': 7}))  # Output: 'banana'
```

**Output:** `'banana'` 🍌

## 5. `group_fruits(fruits:list)`

**Group fruits by their first letter (uppercase), with sorted lists as values.**

### Step-by-Step Solution 🧩

- Loop through each fruit in `fruits`.
- Use the first letter as the key.
- Append the fruit to the corresponding list in a dictionary.
- Sort each list before returning.

```python
def group_fruits(fruits:list):
    grouped = {}
    for fruit in fruits:
        first_letter = fruit[^0]
        if first_letter not in grouped:
            grouped[first_letter] = []
        grouped[first_letter].append(fruit)
    for key in grouped:
        grouped[key].sort()
    return grouped
```


#### Practice Example

```python
print(group_fruits(['Apple', 'Banana', 'Apricot', 'Blueberry', 'Cherry']))
# Output: {'A': ['Apple', 'Apricot'], 'B': ['Banana', 'Blueberry'], 'C': ['Cherry']}
```


## 6. `bin_fruits(fruit_prices)`

**Classify fruits as 'cheap', 'affordable', or 'costly' based on price.**

- Cheap: price < 3
- Affordable: 3 ≤ price ≤ 6
- Costly: price > 6


### Step-by-Step Solution 🧩

- Loop through each fruit and price.
- Add fruit to the appropriate set in the result dictionary.

```python
def bin_fruits(fruit_prices):
    binned_fruits = {'cheap': set(), 'affordable': set(), 'costly': set()}
    for fruit, price in fruit_prices.items():
        if price < 3:
            binned_fruits['cheap'].add(fruit)
        elif 3 <= price <= 6:
            binned_fruits['affordable'].add(fruit)
        else:
            binned_fruits['costly'].add(fruit)
    return binned_fruits
```


#### Practice Example

```python
print(bin_fruits({'apple': 5, 'banana': 2, 'cherry': 7, 'date': 3}))
# Output: {'cheap': {'banana'}, 'affordable': {'apple', 'date'}, 'costly': {'cherry'}}
```


## 🎯 Practice Time!

Try the above functions with your own data to reinforce your understanding. If you have any questions or want more practice, just ask! Happy coding! 😊

<div style="text-align: center">⁂</div>

