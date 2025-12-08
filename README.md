# RL-Project-Robotic-Arm-Control

A comprehensive reinforcement learning project implementing and comparing multiple state-of-the-art RL algorithms for robotic arm control. This project trains agents to perform reaching tasks using the FetchReach environment from Gymnasium Robotics.

## Project Overview

This repository contains implementations of several reinforcement learning algorithms applied to continuous robotic arm control:

- **PPO (Proximal Policy Optimization)**: Stable on-policy algorithm
- **SAC (Soft Actor-Critic)**: Sample-efficient off-policy algorithm
- **DDPG/TD3 with HER (Hindsight Experience Replay)**: Advanced off-policy methods with goal-conditioned learning

The project evaluates algorithm performance and robustness under different environment configurations, with demonstrations of learned behaviors.

## Project Structure

```
RL-Project-Robotic-Arm-Control/
├── README.md                          # This file
├── requirements.txt                   # Python dependencies
├── Source_Code/                       # Training implementations
│   ├── PPO.ipynb                     # PPO algorithm implementation
│   ├── SAC.ipynb                     # SAC algorithm implementation
│   └── DDPG_TD3_HER.ipynb           # DDPG/TD3 with HER implementation
└── FetchReach_Demo/                   # Visualizations and demos
    ├── FetchReach Baseline.gif        # Baseline environment demo
    └── FetchReach Modified.gif        # Modified environment demo
```

## Requirements

- Python 3.8+
- MuJoCo physics engine
- Gymnasium Robotics environment

All dependencies are listed in `requirements.txt`.

## Installation

### 1. Clone the Repository

```bash
git clone https://github.com/YazdanRe/RL-Project-Robotic-Arm-Control.git
cd RL-Project-Robotic-Arm-Control
```

### 2. Create a Virtual Environment

```bash
# Using Python venv
python -m venv venv

# Activate virtual environment
# On Windows:
venv\Scripts\activate
# On macOS/Linux:
source venv/bin/activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Verify Installation

```bash
python -c "import gymnasium; import stable_baselines3; import mujoco; print('All dependencies installed successfully!')"
```

## Usage

### Running Training Scripts

Each algorithm is implemented as a Jupyter notebook. You can run them using:

```bash
# Start Jupyter
jupyter notebook

# Then navigate to Source_Code/ and open the desired notebook
```

Alternatively, convert notebooks to scripts and run directly:

```bash
jupyter nbconvert --to script Source_Code/PPO.ipynb
python Source_Code/PPO.py
```

### Available Notebooks

#### 1. PPO (PPO.ipynb)
Implements Proximal Policy Optimization for the FetchReach task.
- **Best for**: Stable training with moderate sample efficiency
- **Characteristics**: On-policy, robust convergence

#### 2. SAC (SAC.ipynb)
Implements Soft Actor-Critic algorithm.
- **Best for**: Sample-efficient training with exploration control
- **Characteristics**: Off-policy, entropy regularization

#### 3. DDPG/TD3 with HER (DDPG_TD3_HER.ipynb)
Advanced off-policy methods with Hindsight Experience Replay.
- **Best for**: Goal-conditioned learning with sparse rewards
- **Characteristics**: Off-policy, goal-relabeling, improved TD3

## FetchReach_Demo

This directory contains pre-recorded demonstrations of trained agents performing the FetchReach task:

- **FetchReach Baseline.gif**: Demonstrates agent performance in the baseline FetchReach environment with standard gravity and dynamics
- **FetchReach Modified.gif**: Demonstrates agent robustness when deployed in a modified environment with altered physics parameters

These demonstrations showcase how the trained models generalize and adapt to environmental variations.

## Dependencies

| Package | Purpose |
|---------|---------|
| gymnasium | RL environment framework |
| gymnasium-robotics | FetchReach environment |
| stable-baselines3 | RL algorithm implementations |
| numpy | Numerical computing |
| pandas | Data manipulation |
| matplotlib | Visualization |
| mujoco | Physics simulation |
| tensorboard | Training visualization |

## Configuration

Training hyperparameters can be adjusted directly in each notebook:
- Learning rates
- Neural network architecture (currently using the default from stable-baselines3)
- Training duration (timesteps)
- Batch sizes
- Discount factors (gamma)
- Entropy coefficients
