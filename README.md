# Genetic Algorithm for Satellite Trajectory Optimization

This MATLAB project demonstrates the use of a **Genetic Algorithm (GA)** to optimize the trajectory of a satellite transferring from one circular orbit to another. The goal is to minimize the total fuel consumption, measured by the total change in velocity (ΔV) during the transfer. This is compared with the standard Hohmann transfer method, which is analytically optimal for two-impulse orbital transfers.

## Problem Overview

A satellite is initially in a circular orbit with a radius of 7000 km. The target is to transfer the satellite to a higher circular orbit with a radius of 10,000 km. The fuel consumption for the transfer is proportional to the total change in velocity (ΔV) during impulsive burns. The **Genetic Algorithm** is used to find the optimal sequence of thrust impulses that minimize the ΔV.

For comparison, we also compute the ΔV for a **Hohmann transfer**, a well-known two-impulse maneuver that is typically used to minimize fuel between circular orbits.

## Features

- **Genetic Algorithm**: Implements population-based optimization to find the best thrust sequence.
- **Standard Hohmann Transfer**: Provides a benchmark for comparison.
- **Plots**: Visualizes the fuel consumption (ΔV) for the GA solution vs. the Hohmann transfer.

## Files

1. **Main Script (`GA_Trajectory_Optimization.m`)**: The main script that runs the GA and compares the result with the Hohmann transfer.
2. **`evaluateThrustSequence.m`**: Function that calculates the fuel consumption (ΔV) for a given thrust sequence.
3. **`selectRoulette.m`**: Implements the roulette wheel selection mechanism for the GA.
4. **`applyCrossover.m`**: Performs crossover between parent individuals to create offspring.
5. **`applyMutation.m`**: Mutates genes of individuals in the population to maintain genetic diversity.

## Usage

1. **Clone the repository**:
   ```bash
   git clone https://github.com/your-repo/GA-Trajectory-Optimization.git
   ```

2. **Run the MATLAB script**:
   Open `GA_Trajectory_Optimization.m` in MATLAB and run the script.

3. **Modify Parameters**:
   You can adjust the following parameters inside the script to experiment with different GA configurations:
   - `populationSize`: Number of individuals in the GA population.
   - `numGenerations`: Number of generations to evolve the population.
   - `mutationRate`: Probability of mutation.
   - `crossoverRate`: Probability of crossover.
   - `numSteps`: Number of impulsive burns.

## Example Output

For 100 generations of the Genetic Algorithm:

```
Generation 100: Best deltaV = 2.450 km/s
Optimal deltaV found by GA: 2.450 km/s
DeltaV for Hohmann transfer: 2.455 km/s
```

### Fuel Consumption Comparison

The code also produces a bar chart that compares the ΔV of the solution found by the Genetic Algorithm with the analytically optimal Hohmann transfer.

### Plot Example:
```
---------------------
|  GA     |  Hohmann |
|  2.450  |   2.455  |
---------------------
```

## Functions

- **`evaluateThrustSequence.m`**: 
   - Calculates the ΔV for a given thrust sequence in the transfer.
   - Considers the velocities at perigee and apogee of the transfer orbit.
  
- **`selectRoulette.m`**:
   - Implements roulette wheel selection based on fitness (ΔV). Lower ΔV corresponds to better fitness.
   
- **`applyCrossover.m`**:
   - Performs crossover between two parents to create two offspring.
   
- **`applyMutation.m`**:
   - Mutates the thrust sequence randomly based on the mutation rate.

## Optimization Flow

1. **Initialize Population**: Random thrust sequences (angles and magnitudes) are generated for the population.
2. **Evaluate Fitness**: Each individual's fitness is computed by calculating the ΔV for the thrust sequence.
3. **Selection**: Individuals are selected based on fitness using roulette wheel selection.
4. **Crossover**: Crossover is applied to create new offspring.
5. **Mutation**: Random mutations are introduced to maintain diversity.
6. **Termination**: The algorithm runs for a predefined number of generations or until convergence.
7. **Comparison**: The best GA solution is compared with the ΔV of a Hohmann transfer.

## License

This project is licensed under the MIT License.

---

Feel free to explore the code and adjust the parameters to suit your needs!
