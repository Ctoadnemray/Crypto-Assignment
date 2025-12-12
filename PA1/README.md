# Prime Detector and Nth Prime Generator  
### Using Naive Trial Division  
Author: Tanmay Gadve  

---

## Overview  
This document explains and contains Python implementations of:

1. **A naive prime detector** using trial division up to √n  
2. **A wrapper detector** that returns 1/0 instead of True/False  
3. **An nth-prime generator** that uses the detector to compute the nth prime  

This approach satisfies the requirement of building an *nth prime generator from a prime detector*.  
The methods are correct, simple, and mathematically justified.

---

## Prime Detector (`is_prime`)
The `is_prime` function checks whether a number is prime by testing divisibility only up to its square root.  

### Key Features:
- Rejects small and even numbers quickly  
- Tests only odd divisors  
- Uses integer square root for efficient looping  

### Code
```python
import math

def is_prime(n: int) -> bool:
    """Return True if n is prime, else False (naive trial division)."""
    if n <= 1:
        return False
    if n <= 3:
        return True
    if n % 2 == 0:
        return False

    limit = int(math.isqrt(n))
    for d in range(3, limit + 1, 2):
        if n % d == 0:
            return False
    return True
