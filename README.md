# QLGA-Task-Scheduling in Cloud Manufacturing

[![Python Version](https://img.shields.io/badge/python-3.8%2B-blue)](https://www.python.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

An implementation of the **Q-Learning Genetic Algorithm (QLGA)** to solve the **Dynamic Task Scheduling and Service Allocation (DTSSA)** problem in Cloud Manufacturing (CMg).

## 📌 Overview
This repository implements a hybrid metaheuristic approach based on the 2026 research paper: *"A reinforcement learning-based metaheuristic approach to address the dynamic scheduling problem in cloud manufacturing with task cancellation"*.

The project addresses the complexity of scheduling tasks among multiple providers while considering real-world dynamic constraints such as:
* **Logistics Time:** Transportation delays between providers.
* **Arrival Time:** Non-simultaneous task entries.
* **Task Cancellation:** Handling system disruptions efficiently.

## 🚀 The Algorithm: QLGA
Standard Genetic Algorithms (GA) often struggle with parameter tuning and premature convergence. This project solves this by integrating **Q-Learning**:
- **State:** Represents the current status of the population (e.g., diversity or fitness stagnation).
- **Action:** Adaptive selection of GA parameters (Crossover/Mutation rates) or operator types.
- **Reward:** Positive feedback (+1) if the fitness improves, guiding the GA toward global optima.

## 📂 Repository Structure
* `src/`: Contains the core logic (`instance_generator.py`, `qlga_model.py`).
* `notebooks/`: Interactive Jupyter Notebook showing the step-by-step execution.
* `docs/`: Reference research paper and technical documentation.
* `requirements.txt`: List of Python dependencies.

## 🛠 Installation & Usage
1. Clone the repo:
   ```bash
   git clone [https://github.com/YOUR_USERNAME/QLGA-Task-Scheduling.git](https://github.com/YOUR_USERNAME/QLGA-Task-Scheduling.git)

   🧠 Technical Deep DiveThis project implements a hybrid QLGA (Q-Learning Genetic Algorithm) to optimize task scheduling. Unlike a standard Genetic Algorithm that uses fixed probabilities, our approach uses a Reinforcement Learning agent to dynamically adjust parameters.1. Mathematical FoundationThe Q-agent updates its knowledge using the Bellman Equation:$$Q_{t+1}(s_t, a_t) = Q_t(s_t, a_t) + \alpha [r_t + \gamma \max_{a} Q_t(s_{t+1}, a) - Q_t(s_t, a_t)]$$Where:$\alpha$ (Learning Rate): $0.1$$\gamma$ (Discount Factor): $0.9$$r_t$ (Reward): Based on fitness improvement.2. Q-Learning Components in this ProjectState Space ($S$): The environment state is defined by the Convergence Rate and Population Diversity. It monitors if the GA is stuck in a local optimum.Action Space ($A$): The agent can choose between 4 sets of GA parameters (varying Crossover and Mutation rates).Reward Function ($R$): * Positive Reward (+1): If the best fitness in the current generation is better than the previous one.Negative/Neutral Reward (0 or -0.1): If the population fails to improve, encouraging the agent to try different GA parameters.3. Chromosome RepresentationEach chromosome represents a potential schedule in Cloud Manufacturing, where:Part 1: Sequence of tasks.Part 2: Assigned Service Providers (SPs) for each sub-task.4. Dynamic Constraints HandledThe code specifically calculates:Logistic Time: $LT = \frac{Distance}{Speed}$, added when sub-tasks move between different providers.Task Cancellation: A dynamic event handler that re-optimizes the schedule when a task is removed from the pipeline.
