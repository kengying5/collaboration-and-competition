## Project report

## Algorithm
<a id="learning-algo"></a>

Algorithm used here is the deep deterministic policy gradient algorithm (ddpg). DDPG is a model-free policy based learning algorithm in which the agent will learn directly from the unprocessed observation spaces without knowing the domain dynamic information.
Unlike project 2, ddpg used here is to ensure that both states and actions are continuous, and that two agents play against each other. There's a symetrical nature of problem as both agents receive same type of reward, observe same type of states and have same actions space. Hence, the first approach was "simply" to re-use/adapt **DDPG algorithm in a multi-agent setting** where each agent:
* store their experiences in a shared replay buffer and;
* share the same actor and critic network.

```
noise = 1.0
min_noise = min_noise
noise_reduction = min_noise**(1/n_episodes)
```

## Parameters

```
# Runner
n_episodes=10000        # maximum number of training episodes
min_noise=0.02            # maximum number of timesteps per episode

# Agent
BUFFER_SIZE = int(1e6)  # replay buffer size
BATCH_SIZE = 512        # minibatch size
GAMMA = 0.99            # discount factor
TAU = 1e-3              # for soft update of target parameters
LR_ACTOR = 1e-3         # learning rate of the actor 
LR_CRITIC = 1e-3        # learning rate of the critic
WEIGHT_DECAY = 0        # L2 weight decay

# Neural Networks (both Actor & Critic)
hidden_layers = [128, 64]
```

## Results

<img src="https://github.com/kengying5/collaboration-and-competition/blob/master/Images/p3-result.PNG" width="300" height="300" >

```
Episode 1600	Average Score: 0.13
Episode 1700	Average Score: 0.31
Episode 1800	Average Score: 0.26
Episode 1900	Average Score: 0.22
Episode 2000	Average Score: 0.28
Episode 2100	Average Score: 0.24
Episode 2200	Average Score: 0.26
Episode 2300	Average Score: 0.39
Episode 2354	Average Score: 0.50
```


## Ideas for future works

1. To tune the model better with hyperparameters
2. Add more noise to the network itself




