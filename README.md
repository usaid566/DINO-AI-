# Chrome Dino Reinforcement Learning AI

A reinforcement learning project where an AI agent learns to play the Chrome Dino game using computer vision, OCR, and automated keyboard controls.

## Overview.

This project creates a custom Gymnasium environment for the Chrome Dino game and trains an AI agent to play automatically using reinforcement learning.

The agent:

* Captures the game screen in real time
* Processes frames using OpenCV
* Detects game-over states using OCR
* Performs actions such as jumping and ducking
* Learns through rewards and penalties

---

# Features

* Real-time screen capture using MSS
* Custom Gymnasium environment
* OCR-based game-over detection using PyTesseract
* Reinforcement learning support with Stable-Baselines3
* Automated gameplay controls using PyAutoGUI
* Frame preprocessing using OpenCV

---

# Technologies Used

| Technology        | Purpose                           |
| ----------------- | --------------------------------- |
| Python            | Core programming language         |
| OpenCV            | Image processing                  |
| Gymnasium         | RL environment framework          |
| Stable-Baselines3 | Reinforcement learning algorithms |
| MSS               | Screen capture                    |
| PyTesseract       | OCR for game-over detection       |
| PyAutoGUI         | Keyboard automation               |
| NumPy             | Numerical operations              |

---

# How It Works

## 1. Screen Capture

The game window is captured continuously using MSS.

## 2. Frame Processing

Frames are converted to grayscale and resized before being passed to the agent.

## 3. Action Selection

The AI selects one of the following actions:

* Jump
* Duck
* No action

## 4. Reward System

The agent receives rewards for surviving longer and penalties for crashing.

## 5. Game Over Detection

OCR is used to detect the "GAME OVER" text from the game screen.

---

# Project Structure

```bash
.
├── main.ipynb
├── environment.py
├── models/
├── logs/
├── screenshots/
├── README.md
└── requirements.txt
```

---

# Installation

## Clone the Repository

```bash
git clone https://github.com/your-username/chrome-dino-rl.git
cd chrome-dino-rl
```

## Create Virtual Environment

```bash
python -m venv venv
```

## Activate Environment

### Windows

```bash
venv\Scripts\activate
```

### Linux / Mac

```bash
source venv/bin/activate
```

## Install Dependencies

```bash
pip install -r requirements.txt
```

---

# Install Tesseract OCR

Download and install Tesseract OCR:

[https://github.com/UB-Mannheim/tesseract/wiki](https://github.com/UB-Mannheim/tesseract/wiki)

Then set the executable path:

```python
pytesseract.pytesseract.tesseract_cmd = r"C:\Program Files\Tesseract-OCR\tesseract.exe"
```

---

# Running the Project

1. Open Google Chrome
2. Navigate to:

```text
chrome://dino/
```

3. Ensure browser zoom is set to 100%
4. Run the notebook or training script

---

# Example Training Loop

```python
for episode in range(10):

    obs, info = env.reset()

    done = False
    total_reward = 0

    while not done:

        action = env.action_space.sample()

        obs, reward, terminated, truncated, info = env.step(action)

        done = terminated or truncated

        total_reward += reward

    print(f"Episode {episode} Reward: {total_reward}")
```

---

# Future Improvements

* Train using PPO or DQN
* Add obstacle detection instead of OCR-only logic
* Improve reward shaping
* Add model checkpoint saving
* Optimize frame preprocessing
* Add TensorBoard monitoring

---

# Learning Objectives

This project demonstrates concepts such as:

* Reinforcement Learning
* Computer Vision
* OCR Integration
* Environment Design
* Automated Gameplay Agents
* Screen-Based AI Interaction

---

# Disclaimer

This project is intended for educational and research purposes only.

---

# Authors

Zain Saqib
Unaiza Rehman 
