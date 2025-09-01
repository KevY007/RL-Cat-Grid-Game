# RL-Cat-Grid-Game
Cat Grid Game using Reinforcement Learning

# 1. Introduction
This project presents a simple grid-world simulation where a cat moves through a grid to catch mice while avoiding dogs and collecting catnip to maintain its health. The game is modeled as a reinforcement learning (RL) problem. The cat learns to optimize its movement based on rewards such as catching mice, avoiding dogs, and collecting catnip. The goal is to create an intelligent agent that navigates the grid effectively using policy iteration.

# 2. Environment
The grid-world is a 5x5 environment where the cat, dogs, mice, and catnip are randomly placed, a default seed and number of mice, dogs and catnips are provided when generating the grid. The cat's objective is to catch mice, avoid dogs, and collect catnip to maintain or restore its health. The state of the cat is described by its position (x, y) and its health (h). The agent can take one of four possible actions: moving up, down, left, or right.
Key components:
•	DOGS: Dangerous obstacles that decrease the cat's health when encountered.
•	MICE: Targets to be caught for rewards.
•	CATNIP: Items that restore health when collected.
•	HEALTH: A value representing the cat's health, which can be reduced by dogs or restored by catnip.

# 3. Initial State
Position: The agent (cat) begins at the position (0, 0) on the grid.
Health: Initial health is set to 40, unless changed. This means the cat has to collect at least one catnip to win and even one dog encounter will cause it to lose -50 health and fail.

# 4. Actions & Rewards
Movement: -1
Encountering a dog: -50 reward and -50 health
Catching a mouse: +100
Collecting catnip: +30 reward and +30 health
Health = 0: Fail/Lose
Collecting all mouse with >= 50 health: Terminal/Win

# 5. Reinforcement Learning Approach
This project employs policy iteration, a classical RL method, to learn an optimal policy for the cat. The algorithm works in two phases:
1.	Policy Evaluation: For each state, the expected value of taking an action is computed using the current policy, and the value function is updated iteratively until convergence.
2.	Policy Improvement: The policy is updated by selecting the action with the highest expected reward based on the value function. This process continues until the policy stabilizes.
The goal of the agent is to learn the optimal policy that maximizes the cumulative reward over time.

# 6. Results and Visualization
The policy is visualized on the grid, showing the optimal action (UP, DOWN, LEFT, RIGHT) to take from each position. The simulation shows the cat's movement and decision-making process. The goal is to capture all mice while avoiding dogs and ensuring the cat's health remains positive.
<img width="967" height="1013" alt="image" src="https://github.com/user-attachments/assets/15f03d88-27a7-446f-b57e-110db022a575" />

