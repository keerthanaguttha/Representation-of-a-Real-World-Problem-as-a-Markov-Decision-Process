# Representation-of-a-Real-World-Problem-as-a-Markov-Decision-Process


## Aim

To model a smart irrigation system for agriculture as a Markov Decision Process (MDP) by defining its states, actions, transition probabilities, rewards, and Python representation.


## Problem Statement

### Problem Description

A smart irrigation system monitors soil moisture and weather conditions to decide when and how much to irrigate crops. The objective is to maintain optimal soil moisture while conserving water and maximising crop health.

## MDP Components

A Markov Decision Process is represented as:

$$
MDP = (S, A, P, R, \gamma)
$$

Where:

| Symbol | Meaning |
|---|---|
| $S$ | Set of states |
| $A$ | Set of actions |
| $P$ | Transition probability function |
| $R$ | Reward function |
| $\gamma$ | Discount factor |

---

## State Space

The state space should list all possible situations in which the agent can exist.
```
S = {
    Dry_Soil,
    Moist_Soil,
    Wet_Soil,
    Rain_Forecast,
    Crop_Healthy,
    Crop_Stressed
}
```
## Sample State

A sample state is one specific example from the state space.
```
Moist_Soil
```
## Action Space

The action space should list all possible actions available to the agent.
```
A = {
    No_Irrigation,
    Light_Irrigation,
    Heavy_Irrigation,
    Delay_Irrigation
}
```
## Sample Action

A sample action is one action selected from the action space.
```
Light_Irrigation
```
## Transition Probability

The transition probability explains how the environment moves from one state to another after an action is taken.

General form:

$$
P(s'\mid s,a)
$$

```
From Dry_Soil, after Light_Irrigation
Moist_Soil = 0.80
Dry_Soil = 0.20
From Moist_Soil, after No_Irrigation
Dry_Soil = 0.60
Moist_Soil = 0.40
```
## Reward Function

The reward function defines the feedback received by the agent after taking an action.

General form:

$$
R(s,a,s')
$$

```
Situation                          	Reward

Crop remains healthy	                  +50
Water conserved	                          +15
Soil reaches ideal moisture            	  +25
Overwatering	                          -20
Crop becomes stressed	                  -40

```
Discount Factor

γ = 0.90

## Graphical Representation

<img width="1055" height="650" alt="image" src="https://github.com/user-attachments/assets/e35e16e2-3e82-4af2-8ab2-f5ca41eb8287" />


## Python Representation

### MDP Representation using Python
### Name : Guttha Keerthana
### Register Number : 212223240045
```
# States
states = {
    "S1": "Dry_Soil",
    "S2": "Moist_Soil",
    "S3": "Wet_Soil",
    "S4": "Crop_Healthy",
    "S5": "Crop_Stressed"
}

# Actions
actions = {
    "A1": "No_Irrigation",
    "A2": "Light_Irrigation",
    "A3": "Heavy_Irrigation",
    "A4": "Delay_Irrigation"
}

# Transition Probabilities P(s' | s, a)
transition_probabilities = {
    ("Dry_Soil", "Light_Irrigation"): {
        "Moist_Soil": 0.8,
        "Dry_Soil": 0.2
    },
    ("Moist_Soil", "No_Irrigation"): {
        "Dry_Soil": 0.6,
        "Moist_Soil": 0.4
    },
    ("Moist_Soil", "Heavy_Irrigation"): {
        "Wet_Soil": 1.0
    },
    ("Wet_Soil", "Delay_Irrigation"): {
        "Crop_Healthy": 1.0
    },
    ("Dry_Soil", "No_Irrigation"): {
        "Crop_Stressed": 1.0
    }
}

# Reward Function R(s, a, s')
rewards = {
    ("Dry_Soil", "Light_Irrigation", "Moist_Soil"): 25,
    ("Moist_Soil", "No_Irrigation", "Dry_Soil"): -5,
    ("Moist_Soil", "Heavy_Irrigation", "Wet_Soil"): -20,
    ("Wet_Soil", "Delay_Irrigation", "Crop_Healthy"): 15,
    ("Dry_Soil", "No_Irrigation", "Crop_Stressed"): -40
}

# Discount Factor
mdp = {
    "States": states,
    "Actions": actions,
    "Transition_Probabilities": transition_probabilities,
    "Rewards": rewards,
    "Discount_Factor": 0.90
}

print("\nMDP Representation\n")

for key, value in mdp.items():
    print(f"{key}:")
    print(value)
    print()
```
## Output
<img width="1801" height="550" alt="image" src="https://github.com/user-attachments/assets/c6f8b9d9-8d43-4565-a92e-270bd928d97c" />


## Result

The smart irrigation system was successfully represented as a Markov Decision Process by defining its states, actions, transition probabilities, reward function, and discount factor.
