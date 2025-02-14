# Simplex Algorithm Implementation in C++

This repository contains a C++ implementation of the **Simplex Algorithm**, a popular method for solving linear programming problems. The code is designed to find the optimal solution for a given linear programming problem by iteratively improving the solution until the optimality conditions are met.

## Table of Contents
1. [Introduction](#introduction)
2. [Code Overview](#code-overview)
3. [How It Works](#how-it-works)
4. [Usage](#usage)
5. [Example](#example)
6. [Dependencies](#dependencies)
7. [Limitations](#limitations)
8. [Future Improvements](#future-improvements)

---

## Introduction

The Simplex Algorithm is a widely used method for solving linear programming problems. It works by moving along the edges of the feasible region (defined by the constraints) to find the optimal solution. This implementation uses a **tableau** to represent the problem and performs pivot operations to iteratively improve the solution.

---

## Code Overview

The code is structured into several functions, each responsible for a specific part of the algorithm:

1. **`findPivotColumn`**: Identifies the pivot column by finding the most negative coefficient in the objective function row.
2. **`findPivotRow`**: Determines the pivot row using the minimum ratio test.
3. **`pivot`**: Performs the pivot operation to update the tableau.
4. **`isOptimal`**: Checks if the current solution is optimal.
5. **`printTableau`**: Prints the current state of the tableau for debugging or visualization.
6. **`displaySolution`**: Extracts and displays the final solution.
7. **`main`**: Initializes the tableau and runs the algorithm.

---

## How It Works

1. **Initialization**: The tableau is initialized with the objective function and constraints.
2. **Pivot Selection**: The algorithm selects a pivot column (most negative coefficient in the objective function) and a pivot row (minimum ratio test).
3. **Pivot Operation**: The tableau is updated using the pivot operation to improve the solution.
4. **Optimality Check**: The algorithm checks if the current solution is optimal. If not, it repeats the pivot selection and operation steps.
5. **Solution Extraction**: Once the optimal solution is found, the algorithm extracts and displays the values of the decision variables and the optimal objective value.

---

## Usage

To use this code, follow these steps:

1. Clone the repository or copy the code into your C++ environment.
2. Compile the code using a C++ compiler (e.g., `g++`):
   ```bash
   g++ simplex.cpp -o simplex
   ```
3. Run the executable:
   ```bash
   ./simplex
   ```

---

## Example

The provided example solves a linear programming problem with 10 variables (`x1` to `x10`) and 2 constraints. The initial tableau is defined in the `main` function:

```cpp
std::vector<std::vector<double>> tableau = {
    {-1, -3, -2, -4, -1, -5, -2, -3, -1, -6, -7, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0},  // Objective function
    {1,  1,  1,  1,  1,  1,  1,  1,  1,  1,  1,  1,  0,  0,  0,  0,  0,  0,  0,  0,  10}, // Constraint 1
    {1,  2,  3,  2,  1,  4,  2,  3,  1,  5,  6,  0,  1,  0,  0,  0,  0,  0,  0,  0,  20}, // Constraint 2
};
```

The output will display the initial tableau, intermediate tableaus after each pivot operation, and the final optimal solution.

---

## Dependencies

This implementation uses the following C++ standard libraries:
- `<iostream>`: For input/output operations.
- `<vector>`: For dynamic array storage.
- `<algorithm>`: For utility functions.
- `<iomanip>`: For formatting output.
- `<limits>`: For accessing numeric limits.

No external libraries are required.

---

## Limitations

1. **Problem Size**: The current implementation is limited to small-scale problems due to the use of a simple tableau representation.
2. **Numerical Stability**: The algorithm may encounter numerical instability for problems with very large or very small coefficients.
3. **Constraint Handling**: Only equality constraints are supported in the current implementation. Inequality constraints (e.g., `<=`, `>=`) require additional handling (e.g., slack variables).

---

## Future Improvements

1. **Support for Inequality Constraints**: Extend the implementation to handle inequality constraints by introducing slack, surplus, and artificial variables.
2. **Two-Phase Simplex**: Implement the two-phase simplex method to handle problems with no obvious initial feasible solution.
3. **Input Flexibility**: Allow users to input the problem dynamically (e.g., from a file or command line) instead of hardcoding the tableau.
4. **Performance Optimization**: Optimize the code for larger problems by using sparse matrix representations or parallel processing.

---

Feel free to contribute to this project by opening issues or submitting pull requests!