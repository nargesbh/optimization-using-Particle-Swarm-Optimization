# Finding Global Min and Max Using Particle Swarm Optimization (PSO) Algorithm

## Overview

The Particle Swarm Optimization (PSO) Algorithm is a computational method used to iteratively optimize problems by improving candidate solutions. This project utilizes the PSO algorithm in Python to find the global maximum and minimum of two functions, denoted as f(x, y) and g(x, y), respectively. The objective is to locate points (x, y) that satisfy the following criteria:

### For function f(x, y):
- f(x, y) > 19.2
- Function: 
f(x, y) = |sin(x) * cos(y) * exp(|1 - (√(x^2 + y^2) / π)|)|
- Range: -10 ≤ x, y ≤ 10

### For function g(x, y):
- g(x, y) < -1.7 × 10^6
- Function: 
g(x, y) = x * sin(π * cos(x) * tan(y)) * sin(y / x) / (1 + cos(y / x))
- Range: -100 ≤ x, y ≤ 100

## Implementation

### Requirements
- Python
- NumPy
- mpmath (for high-precision arithmetic)

### Code Structure

The code is structured as follows:

1. **Particle Class**: A `Particle` class represents individual particles within the PSO algorithm. Each particle maintains attributes such as position, velocity, fitness value, and personal best (pbest).

2. **Initialization**: The PSO algorithm initializes a set of particles with random positions and velocities.

3. **Movement for Function f**: The `move_f` function updates particle positions based on the movement rules tailored for function f. It involves random coefficients, personal best, and global best updates while respecting range constraints.

4. **Movement for Function g**: The `move_g` function updates particle positions based on the movement rules designed for function g. Similar to function f, it considers random coefficients, personal best, and global best updates while adhering to range constraints.

5. **Fitness Functions**: The `f` and `g` functions are defined to calculate fitness values for the respective functions. For function f, higher values indicate better fitness, while for function g, lower values represent better fitness.

6. **Global and Personal Best Updates for Function f**: The `best_check_f` function checks and updates the global best (Gbest) and personal best (pbest) for function f.

7. **Global and Personal Best Updates for Function g**: The `best_check_g` function checks and updates the global best (Gbest_g) and personal best (pbest) for function g.

8. **Main Function for Function f**: The `main_f` function runs the PSO algorithm for function f, allowing customization of particle population, coefficients (c1 and c2), and inertia weight (w). It iterates until the global maximum of function f is found.

9. **Main Function for Function g**: The `main_g` function runs the PSO algorithm for function g, enabling adjustments to particle population, coefficients (c1 and c2), and inertia weight (w). It iterates until the global minimum of function g is found.

10. **Plotting Functions**: Functions like `plot` and `plot_g` are provided to visualize the evolution of particles and their positions throughout the optimization process for both functions f and g.

### Key Insights

Through experimentation, it was observed that:
- Lowering the inertia weight (w) and increasing the population size enhances the algorithm's performance.
- Converging to the desired solutions often requires only a few iterations, emphasizing the importance of a sufficient population size.
- Fine-tuning the coefficients c1 and c2 is essential, with balanced values yielding better results.
- The best solution achieved for function g is Gbest_g: [-20.77256532  65.25894549] with Gbest_fit_g: -101314124.91823629.

Feel free to explore and customize the code to suit your specific optimization tasks and parameter preferences.
