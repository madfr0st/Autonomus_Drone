# Drone Delivery Reinforcement Learning Project

This repository contains the implementation of a drone delivery system using reinforcement learning techniques. The project explores different Q-learning methods in both deterministic and stochastic environments.

## 🚁 Project Overview

The project implements a drone delivery simulation where a drone must navigate through a grid environment, pick up packages, and deliver them to their destinations while avoiding obstacles such as eagles and tornadoes. The drone learns optimal policies using Q-learning and Double Q-learning algorithms.

### Environment Features
- **Grid World**: 6x6 grid environment
- **Entities**:
  - 🚁 Drone (agent)
  - 📦 Package pickup locations
  - 🏠 Delivery destinations
  - 🦅 Eagles (obstacles)
  - 🌪 Tornadoes (obstacles)
- **Actions**: Move in cardinal directions, pickup, and dropoff packages
- **Rewards**:
  - Package pickup: +25
  - Package delivery: +100
  - Movement: -2 per step
  - Failed pickup/dropoff attempts: -25/-50

## 🗂 Repository Structure

```
├── part_2_files/                # Part 2 experiment files
│   ├── Q-Tables (PKL files)     # Trained Q-tables for different environments
│   ├── Console Outputs          # Debugging and training logs
│   └── Final Renders            # Final episode visualizations
├── part_3_files/                # Part 3 experiment files
│   └── part_3_q_table.pkl       # Stock Market Q-Table
├── NVDA.csv                     # Dataset for Part 3
├── ssaurav_assignment1_part1.ipynb  # Part 1 implementation
├── ssaurav_assignment1_part2.ipynb  # Part 2 implementation
├── ssaurav_assignment1_part3.ipynb  # Part 3 implementation
```

## 📝 Detailed File Descriptions

### Part 2 Files

#### Q-Table Pickle Files
- **deterministic_q_table.pkl**: Q-learning table for deterministic environment
- **deterministic_double_q_table.pkl**: Double Q-learning table for deterministic environment
- **stochastic_q_table.pkl**: Q-learning table for stochastic environment
- **stochastic_double_q_table.pkl**: Double Q-learning table for stochastic environment
- **hyperparams_[1-6]_stochastic_q_table.pkl**: Q-tables for different hyperparameter configurations
- **hyperparams_base_stochastic_q_table.pkl**: Q-table for baseline hyperparameters

#### Console Output Files
- **train_agent_[environment]_[algorithm]_console_output.txt**: Training logs for debugging
- **evaluate_agent_[environment]_[algorithm]_console_output.txt**: Evaluation logs for debugging

#### Final Render Files
- **final_evaluate_agent_[environment]_[algorithm].txt**: Final episode render visualizations
- **final_evaluate_hyperparams_[#]_stochastic_q.txt**: Final renders for hyperparameter experiments

### Part 3 Files
- **part_3_q_table.pkl**: Trained Q-table for stock market trading environment

### Jupyter Notebooks
- **ssaurav_assignment1_part1.ipynb**: Environment implementation and setup
- **ssaurav_assignment1_part2.ipynb**: Q-learning and Double Q-learning implementations and experiments
- **ssaurav_assignment1_part3.ipynb**: Application of RL to stock market trading

## 🎮 Sample Visualization

Below is a sample visualization of the drone navigating the environment:

```
📦 ⬜ ⬇ ⬜ ⬜ ⬜
⬜ ➡ 🌪 ⬅ ⬜ 🎁
⬜ ⬜ ⬆ ⬜ 🏠 ⬜
⬜ ⬜ ⬜ 🦅 ⬜ ⬜
🚁 ⬜ ⬜ 🦅 ⬜ ⬜
⬜ ⬜ ⬜ ⬜ ⬜ ⬜
```

## 🧪 Experiments

### Part 2: Deterministic vs. Stochastic Environments
- Comparison of Q-learning and Double Q-learning in deterministic environments
- Analysis of algorithm performance in stochastic environments
- Hyperparameter optimization studies with different configurations:
  - Learning rates
  - Discount factors
  - Exploration rates

### Part 3: Stock Market Application
- Application of Q-learning to NVIDIA stock trading
- State representation based on stock price movements
- Actions: Buy, Sell, Hold

## 🏆 Results

Sample results from evaluation:
- Evaluation Episode 1: 47 steps with a total reward of -47
- Successfully completed task with all packages delivered
- Learned to navigate around obstacles and optimize delivery routes

## 📊 Performance Metrics

The agent's performance is evaluated based on:
- Total reward accumulated
- Number of steps to complete deliveries
- Success rate in package delivery
- Ability to avoid obstacles

## 🛠️ Technologies Used

- Python
- NumPy
- Pickle (for saving/loading Q-tables)
- Jupyter Notebooks

## 💻 How to Run

1. Clone the repository
2. Install the required dependencies
3. Open and run the Jupyter notebooks in order:
   ```
   jupyter notebook ssaurav_assignment1_part1.ipynb
   jupyter notebook ssaurav_assignment1_part2.ipynb
   jupyter notebook ssaurav_assignment1_part3.ipynb
   ```
4. To evaluate a trained agent, load the appropriate Q-table and use the evaluation functions provided in the notebooks.




## Model Output

```bash
add this alsoEvaluation Episode 1: Steps: 47 | Total Reward: -47
Task complete count: 1
--- Evaluation Episode 1 starting ---
📦 ⬜ ⬇ ⬜ ⬜ ⬜
⬜ ➡ 🌪 ⬅ ⬜ 🎁
⬜ ⬜ ⬆ ⬜ 🏠 ⬜
⬜ ⬜ ⬜ 🦅 ⬜ ⬜
🚁 ⬜ ⬜ 🦅 ⬜ ⬜
⬜ ⬜ ⬜ ⬜ ⬜ ⬜
Drone moved to (4, 1). Step reward: -2
📦 ⬜ ⬜ ⬇ ⬜ ⬜
⬜ 🛖 ⬅ 🌪 ➡ 🎁
⬜ ⬜ ⬜ ⬆ 🏠 ⬜
⬜ ⬜ ⬜ 🦅 ⬜ ⬜
⬜ 🚁 ⬜ 🦅 ⬜ ⬜
⬜ ⬜ ⬜ ⬜ ⬜ ⬜
Evaluation Episode 1 - Step 1
Drone moved to (3, 1). Step reward: -2
📦 ⬜ ⬇ ⬜ ⬜ ⬜
⬜ ⬅ 🌪 ➡ ⬜ 🎁
⬜ ⬜ ⬆ ⬜ 🏠 ⬜
⬜ 🚁 ⬜ 🦅 ⬜ ⬜
⬜ ⬜ ⬜ 🦅 ⬜ ⬜
⬜ ⬜ ⬜ ⬜ ⬜ ⬜
Drone moved to (2, 1). Step reward: -2
📦 ⬜ ⬜ ⬇ ⬜ ⬜
⬜ 🛖 ⬅ 🌪 ➡ 🎁
⬜ 🚁 ⬜ ⬆ 🏠 ⬜
⬜ ⬜ ⬜ 🦅 ⬜ ⬜
⬜ ⬜ ⬜ 🦅 ⬜ ⬜
⬜ ⬜ ⬜ ⬜ ⬜ ⬜
Drone moved to (1, 1). Step reward: -2
📦 ⬜ ⬜ ⬇ ⬜ ⬜
⬜ 🚁 ⬅ 🌪 ➡ 🎁
⬜ ⬜ ⬜ ⬆ 🏠 ⬜
⬜ ⬜ ⬜ 🦅 ⬜ ⬜
⬜ ⬜ ⬜ 🦅 ⬜ ⬜
⬜ ⬜ ⬜ ⬜ ⬜ ⬜
Action 0 repeated 4 times. Switching to a new action.
Attempted dropoff failed (no package carried). Penalty -50
Drone moved to (0, 1). Step reward: -2
📦 🚁 ⬜ ⬇ ⬜ ⬜
⬜ 🛖 ⬅ 🌪 ➡ 🎁
Page of
186 199
⬜ ⬜ ⬜ ⬆ 🏠 ⬜
⬜ ⬜ ⬜ 🦅 ⬜ ⬜
⬜ ⬜ ⬜ 🦅 ⬜ ⬜
⬜ ⬜ ⬜ ⬜ ⬜ ⬜
Drone moved to (0, 0). Step reward: -2
🚁 ⬜ ⬜ ⬜ ⬇ ⬜
⬜ 🛖 ⬜ ⬅ 🌪 ➡
⬜ ⬜ ⬜ ⬜ ⬆ ⬜
⬜ ⬜ ⬜ 🦅 ⬜ ⬜
⬜ ⬜ ⬜ 🦅 ⬜ ⬜
⬜ ⬜ ⬜ ⬜ ⬜ ⬜
Picked up package 2 for 25 reward
Drone moved to (0, 1). Step reward: -2
⬜ 🚁 ⬜ ⬜ ⬜ ⬜
⬜ 🛖 ⬜ ⬜ ⬇ 🎁
⬜ ⬜ ⬜ ⬅ 🌪 ➡
⬜ ⬜ ⬜ 🦅 ⬆ ⬜
⬜ ⬜ ⬜ 🦅 ⬜ ⬜
⬜ ⬜ ⬜ ⬜ ⬜ ⬜
Drone moved to (1, 1). Step reward: -2
⬜ ⬜ ⬜ ⬜ ⬜ ⬜
⬜ 🚁 ⬜ ⬜ ⬜ 🎁
⬜ ⬜ ⬜ ⬜ ⬇ ⬜
⬜ ⬜ ⬜ ⬅ 🌪 ➡
⬜ ⬜ ⬜ 🦅 ⬆ ⬜
⬜ ⬜ ⬜ ⬜ ⬜ ⬜
Delivered package_2 for +100 reward
Evaluation Episode 1 - Step 11
Drone moved to (1, 0). Step reward: -2
⬜ ⬜ ⬜ ⬜ ⬜ ⬜
🚁 ✅ ⬜ ⬜ ⬜ 🎁
⬜ ⬜ ⬜ ⬜ 🏠 ⬜
⬜ ⬜ ⬜ 🦅 ⬇ ⬜
⬜ ⬜ ⬜ ⬅ 🌪 ➡
⬜ ⬜ ⬜ ⬜ ⬆ ⬜
Drone moved to (1, 1). Step reward: -2
⬜ ⬜ ⬜ ⬜ ⬜ ⬜
⬜ 🚁 ⬜ ⬜ ⬜ 🎁
⬜ ⬜ ⬜ ⬜ ⬇ ⬜
⬜ ⬜ ⬜ ⬅ 🌪 ➡
⬜ ⬜ ⬜ 🦅 ⬆ ⬜
⬜ ⬜ ⬜ ⬜ ⬜ ⬜
Drone moved to (1, 0). Step reward: -2
Page of
187 199
⬜ ⬜ ⬜ ⬜ ⬜ ⬜
🚁 ✅ ⬜ ⬜ ⬜ 🎁
⬜ ⬜ ⬜ ⬜ 🏠 ⬜
⬜ ⬜ ⬜ 🦅 ⬇ ⬜
⬜ ⬜ ⬜ ⬅ 🌪 ➡
⬜ ⬜ ⬜ ⬜ ⬆ ⬜
Drone moved to (1, 1). Step reward: -2
⬜ ⬜ ⬜ ⬜ ⬜ ⬜
⬜ 🚁 ⬜ ⬜ ⬜ 🎁
⬜ ⬜ ⬜ ⬜ 🏠 ⬜
⬜ ⬜ ⬜ ⬇ ⬜ ⬜
⬜ ⬜ ⬅ 🌪 ➡ ⬜
⬜ ⬜ ⬜ ⬆ ⬜ ⬜
Drone moved to (1, 0). Step reward: -2
⬜ ⬜ ⬜ ⬜ ⬜ ⬜
🚁 ✅ ⬜ ⬜ ⬜ 🎁
⬜ ⬜ ⬜ ⬜ 🏠 ⬜
⬜ ⬜ ⬜ ⬇ ⬜ ⬜
⬜ ⬜ ⬅ 🌪 ➡ ⬜
⬜ ⬜ ⬜ ⬆ ⬜ ⬜
Drone moved to (1, 1). Step reward: -2
⬜ ⬜ ⬜ ⬜ ⬜ ⬜
⬜ 🚁 ⬜ ⬜ ⬜ 🎁
⬜ ⬜ ⬜ ⬜ 🏠 ⬜
⬜ ⬜ ⬇ 🦅 ⬜ ⬜
⬜ ⬅ 🌪 ➡ ⬜ ⬜
⬜ ⬜ ⬆ ⬜ ⬜ ⬜
Drone moved to (1, 0). Step reward: -2
⬜ ⬜ ⬜ ⬜ ⬜ ⬜
🚁 ✅ ⬜ ⬜ ⬜ 🎁
⬜ ⬜ ⬇ ⬜ 🏠 ⬜
⬜ ⬅ 🌪 ➡ ⬜ ⬜
⬜ ⬜ ⬆ 🦅 ⬜ ⬜
⬜ ⬜ ⬜ ⬜ ⬜ ⬜
Drone moved to (1, 1). Step reward: -2
⬜ ⬜ ⬜ ⬜ ⬜ ⬜
⬜ 🚁 ⬇ ⬜ ⬜ 🎁
⬜ ⬅ 🌪 ➡ 🏠 ⬜
⬜ ⬜ ⬆ 🦅 ⬜ ⬜
⬜ ⬜ ⬜ 🦅 ⬜ ⬜
⬜ ⬜ ⬜ ⬜ ⬜ ⬜
Drone moved to (0, 1). Step reward: -2
⬜ 🚁 ⬜ ⬜ ⬜ ⬜
Page of
188 199
⬜ ✅ ⬜ ⬜ ⬜ 🎁
⬜ ⬜ ⬇ ⬜ 🏠 ⬜
⬜ ⬅ 🌪 ➡ ⬜ ⬜
⬜ ⬜ ⬆ 🦅 ⬜ ⬜
⬜ ⬜ ⬜ ⬜ ⬜ ⬜
Drone moved to (0, 0). Step reward: -2
🚁 ⬜ ⬜ ⬜ ⬜ ⬜
⬜ ✅ ⬜ ⬜ ⬜ 🎁
⬜ ⬜ ⬜ ⬇ 🏠 ⬜
⬜ ⬜ ⬅ 🌪 ➡ ⬜
⬜ ⬜ ⬜ ⬆ ⬜ ⬜
⬜ ⬜ ⬜ ⬜ ⬜ ⬜
Evaluation Episode 1 - Step 21
Drone moved to (0, 1). Step reward: -2
⬜ 🚁 ⬜ ⬜ ⬜ ⬜
⬜ ✅ ⬜ ⬜ ⬜ 🎁
⬜ ⬜ ⬜ ⬜ ⬇ ⬜
⬜ ⬜ ⬜ ⬅ 🌪 ➡
⬜ ⬜ ⬜ 🦅 ⬆ ⬜
⬜ ⬜ ⬜ ⬜ ⬜ ⬜
Drone moved to (0, 0). Step reward: -2
🚁 ⬜ ⬜ ⬜ ⬜ ⬜
⬜ ✅ ⬜ ⬜ ⬇ 🎁
⬜ ⬜ ⬜ ⬅ 🌪 ➡
⬜ ⬜ ⬜ 🦅 ⬆ ⬜
⬜ ⬜ ⬜ 🦅 ⬜ ⬜
⬜ ⬜ ⬜ ⬜ ⬜ ⬜
Drone moved to (0, 1). Step reward: -2
⬜ 🚁 ⬜ ⬜ ⬜ ⬜
⬜ ✅ ⬜ ⬜ ⬜ 🎁
⬜ ⬜ ⬜ ⬜ ⬇ ⬜
⬜ ⬜ ⬜ ⬅ 🌪 ➡
⬜ ⬜ ⬜ 🦅 ⬆ ⬜
⬜ ⬜ ⬜ ⬜ ⬜ ⬜
Drone moved to (0, 0). Step reward: -2
🚁 ⬜ ⬜ ⬜ ⬜ ⬜
⬜ ✅ ⬜ ⬜ ⬜ 🎁
⬜ ⬜ ⬜ ⬇ 🏠 ⬜
⬜ ⬜ ⬅ 🌪 ➡ ⬜
⬜ ⬜ ⬜ ⬆ ⬜ ⬜
⬜ ⬜ ⬜ ⬜ ⬜ ⬜
Drone moved to (0, 1). Step reward: -2
⬜ 🚁 ⬜ ⬜ ⬜ ⬜
Page of
189 199
⬜ ✅ ⬜ ⬇ ⬜ 🎁
⬜ ⬜ ⬅ 🌪 ➡ ⬜
⬜ ⬜ ⬜ ⬆ ⬜ ⬜
⬜ ⬜ ⬜ 🦅 ⬜ ⬜
⬜ ⬜ ⬜ ⬜ ⬜ ⬜
Drone moved to (0, 0). Step reward: -2
🚁 ⬜ ⬜ ⬜ ⬜ ⬜
⬜ ✅ ⬜ ⬜ ⬜ 🎁
⬜ ⬜ ⬜ ⬇ 🏠 ⬜
⬜ ⬜ ⬅ 🌪 ➡ ⬜
⬜ ⬜ ⬜ ⬆ ⬜ ⬜
⬜ ⬜ ⬜ ⬜ ⬜ ⬜
Drone moved to (0, 1). Step reward: -2
⬜ 🚁 ⬜ ⬜ ⬜ ⬜
⬜ ✅ ⬜ ⬜ ⬜ 🎁
⬜ ⬜ ⬇ ⬜ 🏠 ⬜
⬜ ⬅ 🌪 ➡ ⬜ ⬜
⬜ ⬜ ⬆ 🦅 ⬜ ⬜
⬜ ⬜ ⬜ ⬜ ⬜ ⬜
Drone moved to (0, 0). Step reward: -2
🚁 ⬜ ⬜ ⬜ ⬜ ⬜
⬜ ✅ ⬜ ⬜ ⬜ 🎁
⬜ ⬇ ⬜ ⬜ 🏠 ⬜
⬅ 🌪 ➡ 🦅 ⬜ ⬜
⬜ ⬆ ⬜ 🦅 ⬜ ⬜
⬜ ⬜ ⬜ ⬜ ⬜ ⬜
Drone moved to (0, 1). Step reward: -2
⬜ 🚁 ⬜ ⬜ ⬜ ⬜
⬜ ⬇ ⬜ ⬜ ⬜ 🎁
⬅ 🌪 ➡ ⬜ 🏠 ⬜
⬜ ⬆ ⬜ 🦅 ⬜ ⬜
⬜ ⬜ ⬜ 🦅 ⬜ ⬜
⬜ ⬜ ⬜ ⬜ ⬜ ⬜
Drone moved to (0, 2). Step reward: -2
⬜ ⬜ 🚁 ⬜ ⬜ ⬜
⬜ ⬇ ⬜ ⬜ ⬜ 🎁
⬅ 🌪 ➡ ⬜ 🏠 ⬜
⬜ ⬆ ⬜ 🦅 ⬜ ⬜
⬜ ⬜ ⬜ 🦅 ⬜ ⬜
⬜ ⬜ ⬜ ⬜ ⬜ ⬜
Evaluation Episode 1 - Step 31
Drone moved to (1, 2). Step reward: -2
⬜ ⬜ ⬜ ⬜ ⬜ ⬜
Page of
190 199
⬜ ⬇ 🚁 ⬜ ⬜ 🎁
⬅ 🌪 ➡ ⬜ 🏠 ⬜
⬜ ⬆ ⬜ 🦅 ⬜ ⬜
⬜ ⬜ ⬜ 🦅 ⬜ ⬜
⬜ ⬜ ⬜ ⬜ ⬜ ⬜
Drone moved to (1, 3). Step reward: -2
⬜ ⬜ ⬜ ⬜ ⬜ ⬜
⬜ ✅ ⬜ 🚁 ⬜ 🎁
⬜ ⬇ ⬜ ⬜ 🏠 ⬜
⬅ 🌪 ➡ 🦅 ⬜ ⬜
⬜ ⬆ ⬜ 🦅 ⬜ ⬜
⬜ ⬜ ⬜ ⬜ ⬜ ⬜
Drone moved to (2, 3). Step reward: -2
⬜ ⬜ ⬜ ⬜ ⬜ ⬜
⬜ ⬇ ⬜ ⬜ ⬜ 🎁
⬅ 🌪 ➡ 🚁 🏠 ⬜
⬜ ⬆ ⬜ 🦅 ⬜ ⬜
⬜ ⬜ ⬜ 🦅 ⬜ ⬜
⬜ ⬜ ⬜ ⬜ ⬜ ⬜
Drone moved to (2, 4). Step reward: -2
⬜ ⬜ ⬜ ⬜ ⬜ ⬜
⬜ ⬇ ⬜ ⬜ ⬜ 🎁
⬅ 🌪 ➡ ⬜ 🚁 ⬜
⬜ ⬆ ⬜ 🦅 ⬜ ⬜
⬜ ⬜ ⬜ 🦅 ⬜ ⬜
⬜ ⬜ ⬜ ⬜ ⬜ ⬜
Attempted pickup failed. Penalty -25
Attempted pickup failed. Penalty -25
Attempted pickup failed. Penalty -25
Action 4 repeated 4 times. Switching to a new action.
Attempted dropoff failed (no package carried). Penalty -50
Attempted pickup failed. Penalty -25
Attempted pickup failed. Penalty -25
Evaluation Episode 1 - Step 41
Action 4 repeated 4 times. Switching to a new action.
Drone moved to (1, 4). Step reward: -2
⬜ ⬇ ⬜ ⬜ ⬜ ⬜
⬅ 🌪 ➡ ⬜ 🚁 🎁
⬜ ⬆ ⬜ ⬜ 🏠 ⬜
⬜ ⬜ ⬜ 🦅 ⬜ ⬜
⬜ ⬜ ⬜ 🦅 ⬜ ⬜
⬜ ⬜ ⬜ ⬜ ⬜ ⬜
Drone moved to (1, 5). Step reward: -2
⬜ ⬇ ⬜ ⬜ ⬜ ⬜
⬅ 🌪 ➡ ⬜ ⬜ 🚁
Page of
191 199
⬜ ⬆ ⬜ ⬜ 🏠 ⬜
⬜ ⬜ ⬜ 🦅 ⬜ ⬜
⬜ ⬜ ⬜ 🦅 ⬜ ⬜
⬜ ⬜ ⬜ ⬜ ⬜ ⬜
Picked up package 1 for 25 reward
Drone moved to (1, 4). Step reward: -2
⬜ ⬜ ⬜ ⬜ ⬜ ⬜
⬜ ⬇ ⬜ ⬜ 🚁 ⬜
⬅ 🌪 ➡ ⬜ 🏠 ⬜
⬜ ⬆ ⬜ 🦅 ⬜ ⬜
⬜ ⬜ ⬜ 🦅 ⬜ ⬜
⬜ ⬜ ⬜ ⬜ ⬜ ⬜
Drone moved to (2, 4). Step reward: -2
⬜ ⬜ ⬜ ⬜ ⬜ ⬜
⬜ ✅ ⬇ ⬜ ⬜ ⬜
⬜ ⬅ 🌪 ➡ 🚁 ⬜
⬜ ⬜ ⬆ 🦅 ⬜ ⬜
⬜ ⬜ ⬜ 🦅 ⬜ ⬜
⬜ ⬜ ⬜ ⬜ ⬜ ⬜
Delivered package_1 for +100 reward
Task complete: All packages delivered 😎
```


