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
