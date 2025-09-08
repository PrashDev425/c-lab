# Factorial Recursion Explained (with Call Stack)

## Code Reminder

Here:

-   **Base case:** stops recursion → `factorial(0) = 1`
-   **Recursive case:** reduces the problem → `factorial(n) = n × factorial(n-1)`

```c
#include <stdio.h>

int factorial(int n) {
    // Base case
    if (n == 0)
        return 1;
    // Recursive case
    return n * factorial(n - 1);
}

void main() {
    int num = 5;
    printf("Factorial of %d = %d\n", num, factorial(num));
}
```

### What’s happening here?

* **Base case**: If `n == 0`, the function simply returns `1`. This stops the recursion.
* **Recursive case**: If `n > 0`, the function calls itself with a smaller number (`n-1`) and multiplies the result by `n`.

This is how recursion **breaks a big problem into smaller pieces** until it reaches the stopping point.

---

## Example: `factorial(5)`

Let’s see how `factorial(5)` works step by step.

### Building the recursive calls

```c
int factorial(int n) {
    if (n == 0)
        return 1;
    return n * factorial(n - 1);
}
```
Each call depends on the result of the next one:

```
factorial(5) = 5 × factorial(4) = 5 × ( 4 × 3 × 2 × 1 ) = 120
factorial(4) = 4 × factorial(3) = 4 × ( 3 × 2 × 1 ) = 24  
factorial(3) = 3 × factorial(2) = 3 × ( 2 × 1 ) = 6
factorial(2) = 2 × factorial(1) = 2 × ( 1 × 1 ) = 2
factorial(1) = 1 × factorial(0) = 1 × ( 1 ) = 1
factorial(0) = 1 ← base case reached
```

So the program keeps calling itself until it reaches `factorial(0)`.

---

## How the Call Stack Works

The **call stack** is a memory structure that stores information about active function calls.

You can think of it like **a stack of plates**:

* When a function is called, it is **pushed** onto the stack.
* When a function finishes, it is **popped** off the stack.
* The last function pushed is the first one to finish (this is called **LIFO → Last In, First Out**).

---

### Stack trace for `factorial(5)`

**Pushes (function calls happen):**

```
Push factorial(5)
Push factorial(4)
Push factorial(3)
Push factorial(2)
Push factorial(1)
Push factorial(0)   ← base case
```

**Stack at this point (top = latest call):**

```
   Top → | factorial(0) | base case
         | factorial(1) |
         | factorial(2) |
         | factorial(3) |
         | factorial(4) |
Bottom → | factorial(5) |
         +--------------+
            Call Stack
```

---

### Pops (return values come back):

```
Pop factorial(0) → returns 1
Pop factorial(1) → 1 × 1 = 1
Pop factorial(2) → 2 × 1 = 2
Pop factorial(3) → 3 × 2 = 6
Pop factorial(4) → 4 × 6 = 24
Pop factorial(5) → 5 × 24 = 120
```

---

## Final Answer

After all the recursive calls finish and the stack unwinds, we get:

```
factorial(5) = 120
```
