# Apply Discount Function – FreeCodeCamp Lab

This repository contains my completed solution for the **“Build an Apply Discount Function”** lab from FreeCodeCamp.  
The task was to write a Python function that applies a percentage discount to a price while validating the inputs.  
All user stories and automated tests were successfully passed.

---

## 📘 Lab Description

The goal of the lab was to create a function named `apply_discount` that:

- Takes two parameters: `price` and `discount`
- Validates that both inputs are numbers (`int` or `float`)
- Ensures `price` is greater than 0
- Ensures `discount` is between 0 and 100
- Calculates the discount amount
- Returns the final price after applying the discount

This exercise reinforces Python fundamentals such as input validation, conditional logic, and arithmetic operations.

---

## ✅ User Stories Completed

The lab required the following behaviours:

1. A function named **apply_discount** must be defined  
2. The function must accept **price** and **discount**  
3. If `price` is not a number → return `"The price should be a number"`  
4. If `discount` is not a number → return `"The discount should be a number"`  
5. If `price <= 0` → return `"The price should be greater than 0"`  
6. If `discount < 0 or discount > 100` → return `"The discount should be between 0 and 100"`  
7. If inputs are valid → calculate and return the final price

---

## 🧪 Tests Passed

All tests from the lab were passed successfully:

- ✔ `apply_discount(100, 20)` → **80**  
- ✔ `apply_discount(200, 50)` → **100**  
- ✔ `apply_discount(50, 0)` → **50**  
- ✔ `apply_discount(100, 100)` → **0**  
- ✔ `apply_discount(74.5, 20.0)` → **59.6**  
- ✔ Correct error messages for invalid inputs  
- ✔ Correct handling of edge cases  
- ✔ All validation rules implemented

---

## 🧩 Final Solution

```python
# Function to apply a discount 
def apply_discount(price, discount):
    # Validate that price is a number (int or float)
    if not isinstance(price, int) and not isinstance(price, float):
        return 'The price should be a number'
    
    # Validate that discount is a number (int or float)
    if not isinstance(discount, int) and not isinstance(discount, float):
        return 'The discount should be a number'
    
    # Ensure price is positive
    if price <= 0:
        return 'The price should be greater than 0'
    
    # Ensure discount is within a realistic percentage range
    if discount < 0 or discount > 100:
        return 'The discount should be between 0 and 100'

    # Calculate the discount amount
    discount_amount = price * (discount / 100)
    
    # Subtract discount from original price
    final_price = price - discount_amount
    
    # Return the final price after discount
    return final_price
