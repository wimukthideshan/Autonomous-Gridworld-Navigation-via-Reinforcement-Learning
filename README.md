# Optimal Gridworld Navigation using Q-Learning with A* Baseline

## Overview

This project implements and evaluates a **reinforcement learning–based navigation system** in a gridworld environment.  
A **Q-learning agent** is trained to navigate from a start position to a goal while avoiding obstacles in a **maze-like grid**.

To verify correctness and optimality, the learned policy is compared against a **classical A\* search algorithm**, which provides an optimal shortest-path baseline.

The project demonstrates that **model-free reinforcement learning** can learn optimal navigation behaviour comparable to classical search methods, while offering **very fast decision-making after training**.

---

## Key Features

- Maze-like gridworld environment generation  
- Tabular **Q-learning** with epsilon-greedy exploration  
- Reward shaping for efficient navigation  
- Training and evaluation on **two grid sizes** (15×15 and 50×50)  
- **A\*** search implemented as an optimality baseline  
- Comprehensive visualisations:
  - Training curves (episode return, episode length, success rate)
  - Learned greedy paths
  - Exploration heatmaps
  - A\* vs Q-learning comparison plots  
- Fully reproducible experiments using fixed random seeds  

---

## Environment Description

- The environment is a **2D gridworld** consisting of:
  - **Free cells** (traversable)
  - **Wall cells** (blocked)
- The agent starts near the **top-left** of the grid and must reach a goal near the **bottom-right**.
- The action space consists of four movements:
  - Up
  - Right
  - Down
  - Left
- If the agent attempts to move into a wall or outside the grid, it remains in the same position and receives a penalty.

---

## Learning Algorithm

### Q-Learning

The agent uses **tabular Q-learning**, a model-free reinforcement learning algorithm that learns optimal action values through interaction with the environment.

Key aspects of the implementation:
- A **Q-table** stores the estimated value of each action in every state
- An **epsilon-greedy policy** balances exploration and exploitation
- The exploration rate decays gradually over training
- The standard Q-learning update rule is applied after each step

The reward function is designed to encourage:
- Short paths (step penalty)
- Avoiding collisions (wall penalty)
- Reaching the goal efficiently (large terminal reward)

---

## A* Optimality Baseline

To validate correctness, **A\*** search is implemented on the same gridworld representation.

- Uses Manhattan distance as an admissible heuristic
- Guarantees optimal shortest paths in this environment
- Provides:
  - Optimal path length
  - Number of expanded nodes
  - Runtime performance

The learned Q-learning greedy policy is directly compared against A\* results to measure **optimality and efficiency**.

---

## Experimental Results

The agent was trained and evaluated on two environments:

### 15×15 Gridworld
- Q-learning greedy path length matches A\* optimal path
- Optimality gap: **0**
- Success rate: **100%**
- Very fast execution after training

### 50×50 Gridworld
- Q-learning converges to the same optimal path length as A\*
- Optimality gap: **0**
- Success rate: **100%**
- Demonstrates scalability within discrete state spaces

Across both environments, training curves show:
- Decreasing episode length
- Increasing episode return
- Success rate converging to one

---

## Visualisations

The project includes multiple visual outputs to interpret learning behaviour:

- **Training curves** showing convergence behaviour
- **Greedy policy paths** overlayed on the grid
- **Exploration heatmaps** illustrating exploration–exploitation dynamics
- **Side-by-side comparisons** of A\* and Q-learning paths

These visualisations provide both **quantitative and qualitative evidence** of optimal learning.

---

## How to Run

### Requirements

- Python 3.8+
- NumPy
- Matplotlib

Author

Wimukthi Deshan Dassanayake
BSc Computer Science
University of Westminster

License

This project is provided for educational and portfolio purposes.
Please cite appropriately if reused or extended.

