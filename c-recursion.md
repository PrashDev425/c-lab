
# Lab – Recursion in C

---

## Recursion

**Recursion** is a programming technique where a function calls itself to solve a problem.  

It has two main components:

- **Base Case** → condition to stop recursion (avoids infinite loop).  
- **Recursive Case** → the function calls itself with smaller input, reducing the problem until the base case is reached.  

---

## Key Points About Recursion

- **Memory Usage**: Recursive calls use the **stack** → deep recursion may cause **stack overflow**.  
- **Performance**: Some recursive methods (like naive Fibonacci) are slow → optimize with **memoization** or iterative approach.  
- **Readability**: Recursive solutions are often **clearer** for naturally recursive problems.  

---

## Example Problems

---

### **1. Factorial Calculation**

The factorial of a non-negative integer `n` is defined as:

- Base Case → `factorial(0) = 1`
- Recursive Case → `factorial(n) = n * factorial(n - 1)`

#### C Implementation:

```c
#include <stdio.h>

int factorial(int n) {
    // Base case
    if (n == 0)
        return 1;
    // Recursive case
    return n * factorial(n - 1);
}

int main() {
    int num = 5;
    printf("Factorial of %d = %d\n", num, factorial(num));
    return 0;
}
```

**Output:**  
```
Factorial of 5 = 120
```

---

### **2. Fibonacci Sequence**

The Fibonacci sequence is defined as:

- Base Cases → `fibonacci(0) = 0`, `fibonacci(1) = 1`
- Recursive Case → `fibonacci(n) = fibonacci(n - 1) + fibonacci(n - 2)`

---

### **3. Sum of an Array**

The sum of an array can also be solved recursively:

- Base Case → If array size is 0, return 0.  
- Recursive Case → `sum(arr, n) = arr[n-1] + sum(arr, n-1)`
---
