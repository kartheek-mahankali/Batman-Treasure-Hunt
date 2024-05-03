## Project Overview

### Theme
Treasure Island Grid World with map and key as positive rewards and snakes and volcano as negative 
rewards. 

The environment that we chose for this part of the assignment is a Treasure Hunt. Batman is our agent, and his 
goal is to reach the treasure (Goal), which gives him a reward of +30. There are two rewards for him on the way (a 
map and a key), which give him a positive reward +5 and +10 respectively. He needs to avoid obstacles while trying 
to reach the treasure on the way, which is a snake and a volcano, which give him negative rewards -5 and -6 
respectively.

### Algorithms Used

- SARSA (State-Action-Reward-State-Action) is an on-policy reinforcement learning algorithm that learns the optimal 
value function for a given policy. The key idea behind SARSA is to learn the Q-values for each state-action pair and 
use them to guide the agent's behavior towards the optimal policy.

- In this algorithm, the agent follows an epsilon-greedy policy, where it selects the action with the highest Q-value 
with probability (1-e), and a random action with probability (e). 

- The update function for SARSA is: Q(s,a) <- Q(s,a) + alpha * (reward + gamma * Q(s',a') - Q(s,a))

- where Q(s,a) is the Q-value for taking action a in state s, alpha is the learning rate, reward is the reward received 
for taking that action, gamma is the discount factor, s' is the next state, and a' is the action taken in the next state 
according to the current policy.

- Q-learning is an off-policy reinforcement learning algorithm that tries to find the best action to take for the current 
state. It’s considered off-policy because the q-learning function learns from actions that are outside the current 
policy, like taking random actions. More specifically, q-learning seeks to learn a policy that maximizes the total 
reward. When q-learning is performed we create a q-table with same shape of [state, action] and we initialize our 
values to zero. We then update and store our q-values after each episode. This q-table becomes a reference table 
for our agent to select the best action based on the q-value.
The update function is based on the Bellman equation, which incorporates the immediate reward and the 
maximum Q-value of the next state.

- The Q-value update equation in Q-learning is as follows: Q(s,a) <- Q(s,a) + alpha * (reward + gamma max(a) * Q(s', a') - Q(s,a))

- Q(s, a) represents the Q-value of taking action a in state s. alpha is the learning rate, determining the impact of 
the new information compared to the existing Q-value. reward is the immediate reward received after acting a in 
state s. gamma is the discount factor, determining the importance of future rewards. max(Q(s', a')) is the 
maximum Q-value among all possible actions a' in the next state s'.


