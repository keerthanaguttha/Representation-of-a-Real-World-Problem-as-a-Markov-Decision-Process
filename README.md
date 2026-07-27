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

Write your answer here.

Draw the MDP graph.

The graph should include:

1. States as nodes.
2. Actions as arrows.
3. Rewards on transitions.
4. Transition probabilities if applicable.


---

## Python Representation

Write your code here.

Use Python dictionaries to represent the MDP.


```python
# MDP Representation using Python
# print("Name:       ")
# print("Register Number:     ")

```
---
## Output

Write your Python output here.


---

## Result

Write your result here.



---

