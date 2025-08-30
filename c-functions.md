# C Programming Lab – Functions in C

---

## 1. Theory

### What is a Function?

A function is a **block of code that performs a specific task**.  

### Function Declaration (Prototype) & Function Definition

#### Function Declaration (Prototype)

- A function declaration tells the compiler about the **function’s name**, **return type**, and **parameters**.
- It does not contain the body (code) of the function.
- It’s like a promise to compiler define this function somewhere in the program.

**Syntax:**

```c
return_type function_name(parameter_list);
```

**Example:**

```c
int add(int a, int b);
```

#### Function Definition

- A function definition is where you actually write the code (body) of the function.
- It provides the instructions for what the function does.

**Syntax:**

```c
return_type function_name(parameter_list) {
    // function body
}
```

**Example (Definition):**

```c
int add(int a, int b) // function definition
{
    return a + b;
}
```

#### Driver vs Module function

```c
#include <stdio.h>

// Module function Prototype
int square(int num);

// Driver function: controls the program
void main() 
{
    int number = 5;
    int result;
    result = square(number);
    printf("Square of %d is %d\n", number, result);
}

// Module function: performs a specific task
int square(int num) 
{
    return num * num;
}
```

- ``main()`` → Driver function (calls other functions and controls the program flow).

- ``square()`` → Module function (performs the specific task of squaring a number).

### Types of Functions

Based on parameters and return types, functions in C are classified into 4 types:

| Type   | Parameters | Return Type |            Name               |            Example               |
|--------|------------|-------------|-------------------------------|----------------------------------|
| Type 1 | No         | No          | No parameter, no return value | ``void function1()``             |
| Type 2 | Yes        | No          | Parameter, no return value    | ``void function2(int a, int b)`` |
| Type 3 | No         | Yes         | No parameter, returns value   | ``int function3()``              |
| Type 4 | Yes        | Yes         | Parameter and returns value   | ``int function4(int a, int b)``  |

## 2. Task

### Task 1 : 

Write a C program to do **basic arithmetic** using **different types of functions**:

1. **Type 1:** No parameter, no return → Addition (predefined numbers, print result)  
2. **Type 2:** Parameter, no return → Subtraction (numbers from main, print result)  
3. **Type 3:** No parameter, returns value → Multiplication (predefined numbers, return result)  
4. **Type 4:** Parameter and return → Division (numbers from main, return result, handle zero)  

**Input:**

- Type 1 & 3: Numbers inside function  
- Type 2 & 4: Numbers from main  

**Function Declarations:**

```c
void addition();  
void subtraction(int a, int b);  
int multiplication();  
float division(float a, float b);  
```

### Task 2 :

**Project**

Write a **menu-driven C program** to perform **basic banking operations** using **different types of functions**.

1. **Type 1: No parameter, no return**  
   - Display a **welcome message** and show the current balance.  

2. **Type 2: Parameter, no return**  
   - **Deposit** an amount (passed as parameter) into the account and display the new balance.  

3. **Type 3: No parameter, returns value**  
   - Calculate and return **interest earned** on the current balance (``5% fixed``).  

4. **Type 4: Parameter and return**  
   - **Withdraw** a given amount (passed as parameter).  
   - Return the updated balance.  
   - Check for **insufficient funds** before withdrawal.  

5. Use a **menu-driven interface** to allow the user to:  
   - Deposit money  
   - Withdraw money  
   - Check balance  
   - View interest earned  
   - Exit the program  

**Global Variables**

```c
float balance = 0; 
static float interestRate = 5;
```

**Function Declarations:**

```c
void welcome();  
void deposit(float amount);  
float interestEarned();  
float withdraw(float amount);  
```
