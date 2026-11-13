# Multi-Robot Warehouse Coordination Using Deep Reinforcement Learning

## Project Overview

This project explores how multiple robots can coordinate in a shared warehouse environment using Deep Reinforcement Learning.

The robots are assigned packages to collect and deliver while navigating obstacles and narrow shared aisles. The main challenge is to complete deliveries efficiently while avoiding collisions and deadlocks.

We developed a multi-robot warehouse simulation using **Python and Gymnasium** and compared different approaches, including Random Policy, BFS-based Shortest Path, Independent DQN and Shared Double-Dueling DQN.

## Project Objectives

- Develop a multi-robot warehouse simulation environment.
- Enable robots to collect and deliver assigned packages.
- Handle obstacles, shared aisles and robot collisions.
- Compare independent and parameter-shared reinforcement learning approaches.
- Evaluate performance as the number of robots increases.

## Environment

The simulation includes:
- Multiple robots with individual package assignments.
- Warehouse obstacles and narrow shared aisles.
- Five possible actions: Up, Down, Left, Right and Wait.
- Collision handling for both shared destinations and position swaps.

## Algorithms Compared

| Algorithm | Description |
|---|---|
| Random Policy | Selects valid actions randomly |
| Shortest Path | Uses BFS-based distances without robot coordination |
| Independent DQN | Each robot learns using its own network |
| Shared Double-Dueling DQN | Robots share a learning network |

## Results

The two-robot comparison shows that Shared DQN achieved the strongest overall performance in our reported experiment:

| Metric | Random | Shortest Path | Independent DQN | Shared DQN |
|---|---:|---:|---:|---:|
| Success rate | 0.05 | 0.49 | 0.54 | **0.80** |
| Collisions / episode | 7 | 150 | 15 | **11** |
| Makespan (steps) | 147 | 83 | 78 | **43** |

*Values are read from the project's comparison chart.*

### Performance Comparison

![Algorithm comparison](results/comparison_2_robots.png)

### Scalability

![Scalability results](results/scalability.png)

The scalability experiment evaluates performance with two and four robots. It also compares a shared policy trained on two robots with a curriculum-trained policy adapted from two to four robots.

### Training Performance

![Training curves](results/training_curves.png)

## Simulation

The simulation visualisations demonstrate how robots navigate the warehouse, collect packages and avoid collisions.

### Two-Robot Simulation

![Two robot simulation](results/simulations/simulation_aisle_2.gif)

### Four-Robot Simulation

![Four robot simulation](results/simulations/simulation_aisle_4.gif)

## Technologies Used

- Python
- PyTorch
- Gymnasium
- NumPy
- Matplotlib
- Deep Q-Networks (DQN)
- Double DQN
- Dueling DQN

## Project Structure

```text
multi-robot-warehouse-reinforcement-learning/
├── README.md
├── requirements.txt
├── notebooks/
├── report/
├── results/
│   └── simulations/
└── src/
```

## How to Run

1. Clone this repository:

```bash
git clone YOUR_REPOSITORY_URL
```

2. Install the required dependencies:

```bash
pip install -r requirements.txt
```

3. Open the notebook in Jupyter Notebook or Google Colab.

4. Run the cells to create the environment, train the agents and evaluate their performance.

## Limitations and Future Work

- The environment uses a discrete grid rather than continuous robot movement.
- Robot package assignments are predefined.
- More advanced coordination approaches could be explored, including recurrent DQN and value decomposition methods.
- Future work could investigate larger warehouse layouts and more robots.

## Project Report

The complete project report is available in the `report/` folder.

---

**Academic project:** Introduction to Reinforcement Learning  
**Project:** Multi-Robot Pick-and-Deliver with Obstacle and Collision Avoidance in Shared Aisles
