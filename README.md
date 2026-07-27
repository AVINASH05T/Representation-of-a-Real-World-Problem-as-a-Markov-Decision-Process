# Representation-of-a-Real-World-Problem-as-a-Markov-Decision-Process

## NAME : AVINASH T
## REG NO : 212223230026
## Aim

To model a Netflix/YouTube Recommendation System as a Markov Decision Process (MDP) by defining its states, actions, transition probabilities, reward function, and discount factor for optimizing long-term user engagement.


## Problem Statement

To design a recommendation system for a streaming platform such as Netflix or YouTube that intelligently recommends movies or videos to users based on their interests and viewing behaviour. The system aims to maximize long-term user engagement by selecting recommendations that encourage users to watch more content, like videos, and continue using the platform. Since each recommendation influences the user's future behaviour, the problem can be modelled as a Markov Decision Process (MDP).

### Problem Description

A recommendation system, such as those used by Netflix or YouTube, continuously recommends movies or videos to users based on their viewing history, preferences, and interactions. At every step, the system decides which content to recommend next to maximize long-term user engagement and satisfaction.

The user's response, such as watching, skipping, liking, or ending the session, determines the next state of the system. The objective is to recommend content that increases watch time, user retention, and overall platform engagement. Since each recommendation influences future user behaviour, this problem can be represented as a Markov Decision Process (MDP).


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


```text
S = {
    New User,
    Browsing Content,
    Watching Content,
    Liked Content,
    Session Ended
}
```

---

## Sample State

Watching Content

In this state, the user is actively watching a recommended movie or video. The recommendation system observes the user's behaviour and prepares the next recommendation based on the current interaction.

---

## Action Space


```text
A = {
    Recommend Movie,
    Recommend TV Show,
    Recommend Similar Content,
    Recommend Trending Content,
    Recommend New Release
}
```

---

## Sample Action

Recommend Similar Content

In this action, the recommendation system suggests content that is similar to what the user is currently watching or has watched previously. This increases the probability of continued engagement.

---

## Transition Probability

Write your answer here.

The transition probability explains how the environment moves from one state to another after an action is taken.

General form:

$$
P(s' \mid s,a)
$$

This means:

> Probability of reaching next state $s'$ after taking action $a$ in current state $s$.

Example
If the user is Browsing Content and the system recommends a movie:
80% probability that the user starts watching.
20% probability that the user continues browsing.

Similarly,

If the user is Watching Content:
They may like the content.
They may skip it.
They may end the session.

---

## Reward Function

The reward function provides feedback based on the user's response to the recommendation.

General form:

R(s,a,s′)

where:

s = Current state
a = Recommendation made
s′ = Next state
Example Rewards
Transition	Reward
S0 → S1 (User Starts Browsing)	0
S1 → S2 (User Watches Recommended Content)	+20
S2 → S3 (User Likes or Completes Content)	+50
S2 → S1 (User Skips Recommendation)	−10
S3 → S2 (User Watches Another Recommendation)	+30
S2 → S4 (User Ends Session Early)	−20
S3 → S4 (Session Ends After High Engagement)	+100

---

## Graphical Representation

The Markov Decision Process (MDP) for the Netflix/YouTube Recommendation System is represented as a directed graph. Each node represents a user state, and each arrow represents the action taken by the recommendation system. Rewards are assigned based on the user's interaction, and transition probabilities indicate the likelihood of moving to the next state.

<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/d1b668bb-b00c-4e95-9aef-35c310a61036" />


State Labels
S0 – New User
S1 – Browsing Content
S2 – Watching Content
S3 – Liked Content
S4 – Session Ended
Explanation
The user starts in S0 (New User) and enters Browsing Content (S1).
The recommendation system suggests content.
If the user watches the recommendation, the system moves to Watching Content (S2) with Reward = +20 and Probability = 0.8.
If the user skips the recommendation, the reward is −10, and the user remains in the browsing state.
After watching, the user may like or complete the content, moving to S3 with Reward = +50.
If the user ends the session, the process moves to S4 with a Reward = −20.
From Liked Content (S3), recommending similar content can bring the user back to Watching Content (S2) with Reward = +30, increasing long-term engagement.

This graph satisfies all the required MDP components:

States as nodes.
Actions as arrows.
Rewards on transitions.
Transition probabilities on each transition.


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

